# Tarea_POO_Python
# Clase base: Persona
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre  # Atributo público
        self.__edad = edad    # Atributo privado (encapsulación)

    def mostrar_informacion(self):
        return f"Nombre: {self.nombre}, Edad: {self.__edad}"

    def saludar(self):
        return f"Hola, mi nombre es {self.nombre}."


# Clase derivada: Estudiante (herencia)
class Estudiante(Persona):
    def __init__(self, nombre, edad, matricula):
        super().__init__(nombre, edad)
        self.matricula = matricula

    # Sobrescritura de método (polimorfismo)
    def mostrar_informacion(self):
        return f"Nombre: {self.nombre}, Matrícula: {self.matricula}"

    def estudiar(self):
        return f"{self.nombre} está estudiando."


# Clase derivada: Profesor (herencia)
class Profesor(Persona):
    def __init__(self, nombre, edad, especialidad):
        super().__init__(nombre, edad)
        self.especialidad = especialidad

    # Sobrescritura de método (polimorfismo)
    def saludar(self):
        return f"Hola, soy el profesor {self.nombre} y mi especialidad es {self.especialidad}."

    def enseñar(self):
        return f"El profesor {self.nombre} está enseñando {self.especialidad}."


# Programa principal
if __name__ == "__main__":
    # Crear instancias de las clases
    persona = Persona("Carlos", 35)
    estudiante = Estudiante("Ana", 20, "20231001")
    profesor = Profesor("Luis", 45, "Matemáticas")

    # Mostrar información de cada objeto
    print(persona.mostrar_informacion())
    print(persona.saludar())
    print(estudiante.mostrar_informacion())
    print(estudiante.saludar())
    print(estudiante.estudiar())
    print(profesor.mostrar_informacion())
    print(profesor.saludar())
    print(profesor.enseñar())
