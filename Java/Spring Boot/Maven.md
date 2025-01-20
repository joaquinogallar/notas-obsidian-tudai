# Qué es?
Es una herramienta de gestión de proyectos:
- Gestión de dependencias
- Build generation
- Documentación. etc

Para esto utiliza el archivo **POM.xml** (Project Object Model). 
Cada pom.xml tiene un padre y hereda su configuración. El ultimo padre de todos es llamado [superpom](https://maven.apache.org/ref/3.0.4/maven-model-builder/super-pom.html)
![[padre-pom.xml.png]]

Cuando se utilize un comando de maven (mvn) se busca en este archivo POM la configuración necesaria.

Maven viene a solucionar la complejidad de **Ant**. En **Ant**, además de especificar el **Que** se debe hacer también se debe especificar el **Como**. En Maven solo se especifica el **Que**, Maven despues ve como lo hace. 
## Fases del ciclo de construcción de maven (build lifecycle phases) 
1. **Validate** Project Structure.
	- Por defecto maven no hace nada en esta etapa, es decir que no hay tareas a ejecutar dentro de la misma.
	- Se pueden agregar plugins/tareas para validar por ejemplo que la sintaxis se adapte a los estándares de la empresa.
	- Los plugins se agregan dentro de &lt;plugins&gt; del pom
	- Comando: mvn validate
2. **Compile** Source Code.
	- Convierte el código java a código binario.
	- Archivos **".class"**.
	- Genera los archivos dentro de la carpeta target
	- Comando: mvn compile
3. **Test** the code (Unit Testing).
	- Corre los test dentro de la carpeta test.
	- Comando: mvn test
4. **Package** Compiled Code (ex: jar or war).
	- Genera los .jar o .war dentro de la carpeta target
	- Comando: mvn package
5. **Verify** the Integrity of Package.
	- Por defecto maven no hace nada en esta etapa, es decir que no hay tareas a ejecutar dentro de la misma.
	- Se pueden agregar plugins/tareas para verificar por ejemplo que no haya variables, imports u objetos sin usar, catchs vacios, duplicados, etc (**static code analysis**). Para este caso tenemos a [PMD](https://maven.apache.org/plugins/maven-pmd-plugin/).
	- Comando: mvn verify
6. **Install** the package in **[[Local Repository]]**.
	- Instala nuestro .jar en el **Local Maven Repository** el cual usualmente esta ubicado en nuestro directorio home una vez descargamos maven (/.m2/repository).
	- Esta ubicacion se puede cambiar en el archivo **settings.xml** ubicado en la carpeta **.m2**.
	- Comando: mvn install
7. **Deploy** the package in **Remote Repository**.
	- Hace el deploy de .jar al repositorio remoto (company central o maven central).
	- Si no se define un &lt;distributionManagment&gt; &lt;/distributionManagment&gt; nos va a dar error.
	- Comando: mvn deploy

Cada fase tiene un numero de tareas a ejecutar. Se pueden añadir nuevas tareas de ser necesario.

![[plugins-tasks.png]]

Estas fases son secuenciales, es decir que si queremos ejecutar la fase 4 (package) antes se deben ejecutar las fases anteriores. Lo mismo pasa con las **tareas de cada fase**. Si la fase 4 tiene 10 tareas y queremos ejecutar la tarea 4, primero se ejecutan todas las tareas de todas las fases anteriores a la misma.

La etiqueta &lt;build&gt; &lt;/build&gt; del archivo pom.xml sirve para añadir nuevas tareas en alguna fase especifica del ciclo de vida de maven.

Cuando Maven comienza a buscar las dependencias de nuestro proyecto primero se fija en el **Local Repository**, si la dependencia no se encuentra allí entonces busca en el **Remote Repository** (maven central) lo descarga y lo pone el el Local Repository.
![[Dependencias]]