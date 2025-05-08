# Fuerza Bruta contra un Servidor FTP

En este laboratorio pondrás en práctica técnicas de exploración, fuerza bruta y escalada de privilegios en un entorno controlado. Tu misión es acceder a un servidor FTP, descubrir credenciales débiles y obtener dos flags ocultas. En este laboratorio aprenderas:


- Análisis de servicios mal configurados (FTP anónimo)
- Uso de diccionarios de contraseñas reales
- Ejecución de ataques de fuerza bruta
- Escalada de privilegios en sistemas operativos Linux

<how-to-start>
   
## 🌱 Cómo iniciar este laboratorio

Sigue las siguientes instrucciones para comenzar:

1. **Descarga la máquina virtual** desde este [enlace](https://storage.googleapis.com/cybersecurity-machines/ftp-4geeks-lab.ova).
2. **Importa la máquina** en tu gestor de virtualización preferido (VirtualBox, VMware, etc.).
3. Una vez iniciada la máquina, ¡ya puedes comenzar con el laboratorio!
</how-to-start>


## 📄 Instrucciones

- El servidor tiene habilitado el acceso anónimo vía FTP.
- Se han encontrado indicios de malas prácticas en el uso de contraseñas.
- Algunos usuarios del sistema podrían estar utilizando contraseñas débiles.
- Es tu responsabilidad investigar y explotar las configuraciones vulnerables.


1. **Conectarte como usuario anónimo**

   - Usa un cliente FTP para conectarte con el usuario `anonymous`.
   - Explora los archivos disponibles.
   - Pon atención a posibles pistas.

2. **Realizar un ataque de fuerza bruta**

   - Usa una herramienta como `hydra` junto con un diccionario de contraseñas.
   - Tu objetivo es obtener acceso como ciertos usuarios del sistema.

3. **Obtener la primera flag**

   - Una vez dentro del sistema como usuario válido, revisa su directorio personal.
   - Busca la flag.

4. **Escalar privilegios**

   - Descubre cómo obtener permisos de administrador (root) usando otro usuario del sistema.
   - Recupera la segunda flag desde una ubicación protegida.


## Flag #1

- 📁 Ubicación: en el directorio de uno de los usuarios  
- 🔑 Requiere: encontrar sus credenciales mediante fuerza bruta


## Flag #2

- 📁 Ubicación: en un área del sistema restringida  
- 🔑 Requiere: escalar privilegios hasta obtener acceso como administrador

## Herramientas recomendadas

- Cliente FTP (`ftp`)
- `hydra`
- Diccionario de contraseñas como `rockyou.txt` (disponible en muchas distribuciones de seguridad)

**Recuerda:** no hay soluciones mágicas. Observa, razona y utiliza las herramientas adecuadas. El conocimiento es tu mejor aliado.

¡Feliz Hackeo!
