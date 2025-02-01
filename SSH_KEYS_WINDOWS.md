
# TENER MULTICUENTAS DE GITHUB CON SSH
# ******************* COMANDOS *******************
- Cambiar el correo con el de tu cuenta.
- Cambiar "github-account1" por el nombre de tu preferencia.

```bash
# [1] Generar la llave privada & pública para la cuenta.

ssh-keygen -t ed25519 -C "correo@gmail.com" -f github-account1

# Iniciar el agente SSH para gestionar las llaves.
eval $(ssh-agent -s)

# Agregar la llave privada al agente SSH para gestionar las conexiones (dentro de la carpeta .ssh).
ssh-add ~/.ssh/github-cyanx98

```

```bash
# [2] Configuración de las cuentas a conectar vía SSH.

# - "github-account1": alias que usarás para identificar la cuenta.
# - "IdentityFile" apunta a la llave privada correspondiente.
Host github-account1
  Hostname github.com
  IdentityFile ~/.ssh/github-account1
  IdentitiesOnly yes
  User git
```

```bash
# [3.1] Inicializar repositorio // [3.2] Clonar repositorio

git init                     // git clone
```

```bash
# [4] Establecer correo de la cuenta cada que inicializamos o clonamos un repositorio.
git config user.email "correo@gmail.com"
```

```bash
# [5] Agregar cambios
git add .

# [6] Guardar cambios
git commit -m "first commit"

# [7] Conectar con repositorio remoto
git remote add origin

# [8] Publicar cambios
git push origin master

```


