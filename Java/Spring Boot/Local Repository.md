Esta en nuestra pc.

Con el comando "mvn install" por defecto se hace el deploy en este **Local Repository**. Una vez se ejecute este comando se van a copiar las carpetas de nuestro proyecto (com.x.y) en la ruta que hayamos definido en settings.xml.

La central de maven seria nuestro **Remote Repository** ([maven central](https://mvnrepository.com/repos/central)).

**Maven Central** es publico. Cualquiera puede publicar en el.

En una empresa se trabaja en una network donde la misma tiene su propio remote repository.