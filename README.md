# 2.4-ChatGTP

```python
import network
import urequests

# Configura la conexión Wi-Fi
wifi = network.WLAN(network.STA_IF)
wifi.active(True)
wifi.connect("nombre_de_red", "contraseña_de_red")

# Espera a que se conecte a la red
while not wifi.isconnected():
    pass
print("Conexión Wi-Fi establecida")

# URL de la API de ChatGPT
url = "URL_de_la_API_de_ChatGPT"

# Encabezados (asegúrate de incluir los necesarios para autenticación, si es necesario)
headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer tu_token_de_autenticación"  # Reemplaza con tu token, si es necesario
}

# Realiza la solicitud GET a la API
response = urequests.get(url, headers=headers)

if response.status_code == 200:
    data = response.json()
    curiosidad = data.get("curiosidad")
    print("Dato curioso:", curiosidad)
else:
    print("Error al obtener el dato curioso. Código de estado:", response.status_code)

# Cierra la conexión
response.close()


```
