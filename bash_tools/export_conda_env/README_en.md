# 🧠 Conda Environment Exporter & Transfer Script

This Bash script automates the process of **exporting all Conda environments (except `base`) to `.yaml` files** and **transferring them to a remote machine** using `scp`.

It's ideal for **backing up**, **sharing**, or **migrating Conda environments between systems**.

---

## 🚀 Features

- ✅ **Exports** all Conda environments (except `base`) to `.yaml` files
- 📤 **Transfers** the files to a remote machine using `scp`
- 🧹 **Cleans up** the temporary directory after transfer
- 📋 **User-friendly output** to track progress in the terminal

---

## 🧰 How It Works

1. Creates a temporary directory (`./entornos_yaml`)
2. Loops through all Conda environments (excluding `base`)
3. Exports each environment to a `.yaml` file
4. Uses `scp` to copy the files to a remote machine
5. Deletes the temporary folder after transfer

---

## 📋 Requirements

Before using this script, ensure you have:

- ✅ **Bash shell** (Linux, macOS, or WSL on Windows)
- ✅ **Conda** installed and working
- ✅ **SSH access** to the target machine (for `scp` usage)

---

## ⚙️ Configuration

At the top of the script, you can customize the following variables:

```bash
USUARIO_DESTINO="ion"          # Remote username
MAQUINA_DESTINO="192.168.98.102"  # Remote IP or hostname
DIRECTORIO_DESTINO="~/"        # Remote directory to store YAML files
```

### Example Configuration:
```bash
USUARIO_DESTINO="remote_user"
MAQUINA_DESTINO="myserver.com"
DIRECTORIO_DESTINO="/home/remote_user/conda_envs/"
```

---

## 🧪 Example Usage

```bash
# Make the script executable
chmod +x export_conda_envs.sh

# Run the script
./export_conda_envs.sh
```

---

## 📂 Output

```
Exportando los entornos de Conda...
Exportando entorno: myenv1
Exportando entorno: myenv2
Todos los entornos han sido exportados a la carpeta ./entornos_yaml.
Copiando los archivos YAML a ion@192.168.98.102:~/
¡Archivos transferidos exitosamente!
Carpeta temporal eliminada. Proceso completado.
```

---

## 🛠️ Want to Improve This?

You could enhance the script by adding:

- [ ] ✅ Option to import environments on the remote machine
- [ ] 📤 Logging to a file
- [ ] 🔐 SSH key support or password prompt
- [ ] 📁 Create remote directory if it doesn’t exist

---
