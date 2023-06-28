import subprocess

def connect_to_wifi(ssid, pin):
    command = f'netsh wlan connect name="{ssid}" keyMaterial="{pin}"'
    result = subprocess.run(command, shell=True, capture_output=True, text=True)

    if result.returncode == 0:
        print(f"Successfully connected to Wi-Fi network '{ssid}'!")
    else:
        print(f"Failed to connect to Wi-Fi network '{ssid}'.")

# Usage
wifi_ssid = "Your_WiFi_SSID"
wps_pin = "Your_WPS_PIN"

connect_to_wifi(wifi_ssid, wps_pin)
