Se pueden tener varios estados y de diferentes tipos, pero en general nunca se usa Stateful.
# Stateful
- El estado esta en los serivdores.
- Los servidores tienen que hablar entre si.
```Java
int i = 0;
int count() {
	i++;
	return i;
}
```

# Stateless
## Opción 1
- Cada uno de los clientes tiene su propio estado.
- El servidor es el encargado de calcular el siguiente estado.
```Java
int count(int i) {
	int a = i + 1;
	return a;
}
```
## Opción 2
- El estado se almacena en una base de datos.
- Si hay mas de una base de datos estas tienen que hablar entre si
```Java
int count() {
	int a = dbase.get(cont);
	dbase.write(cont, a++);
	return a;
}
```

# Inyección de Dependencias
