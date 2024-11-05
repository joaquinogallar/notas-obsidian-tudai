# Qué es?
- Es una condición lógica insertada en el código fuente que se **asume cierta**. El sistema se encarga de comprobarlas y disparar **excepciones** en caso de **no** cumplirse.
- Útil en implementación y testeo - Overhead en producción.
- Útil para debuging de un código en producción que está causando problemas.

## Motivación
- Código no alcanzable.
- Diseño por contrato.
	- **Precondición**: Que asumimos como cierto al comenzar el programa.
	- **Postcondición**: Que asumimos como cierto al terminar el programa.
	- **Invariante (de bucle)**: Que se asume como cierto durante la ejecución del programa.

## Contexto
### Si Usarlas
- A la entrada de métodos privados.
- A la salida de métodos.
- Para corroborar las variables y estructuras de datos internas.
- En estructuras de control **else** y **switch** cuando todos los casos correctos están explícitos (es decir, cuando la rama **else** no debería tomarse jamás).
- En bucles largos.

### No Usarlas
- A la entrada de métodos públicos.
- Para detectar errores en los datos de entrada al programa.

# Ejemplo Java
```Java
public void AsignarTarea(Tarea t){
	if(t==null)
		throw new JavaLangNullPointerExeption(“La tarea no existe”);
	t.setResponsable(this);
	assert (t.getResponsable ()==this);
}

private void AsignarTarea(Tarea t){
	assert t: “La tarea no existe”;
	t.setResponsable(this);
	assert (t.getResponsable ()==this);
}
```

https://assertj.github.io/doc/

# Assertion vs Verify
**Assert**: Evalúa una condición, si esa condición no es verdadera, falla el test y se ***detiene***.
**Verify (SoftAssert)**: Evalúa una condición, si esa condición no es verdadera, marca el test como fallido, pero ***continúa*** con la ejecución del test.