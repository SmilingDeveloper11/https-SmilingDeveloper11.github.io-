import pygame
import requests
import platform
import psutil
import time
import datetime
import random
import moviepy.editor as mp
from threading import Thread

# Inicializar pygame
pygame.init()

# Obtener la información de la pantalla
info = pygame.display.Info()
screen_width, screen_height = info.current_w, info.current_h

# Configurar la ventana en pantalla completa
screen = pygame.display.set_mode((screen_width, screen_height), pygame.FULLSCREEN)
pygame.display.set_caption('')

# Colores
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)

# Fuente inicial
font_size = 36
font = pygame.font.Font(None, font_size)

# Cargar música y reproducir en bucle
pygame.mixer.music.load('music.mp3')
pygame.mixer.music.play(-1)

# Obtener la información del sistema
def get_system_info():
    ip_data = requests.get('https://ipapi.co/json/').json()
    
    info = {
        'IP Address': ip_data.get('ip', 'N/A'),
        'Country': ip_data.get('country_name', 'N/A'),
        'Region': ip_data.get('region', 'N/A'),
        'City': ip_data.get('city', 'N/A'),
        'ZIP Code': ip_data.get('postal', 'N/A'),
        'Full Location': f"{ip_data.get('city', 'N/A')}, {ip_data.get('region', 'N/A')}, {ip_data.get('country_name', 'N/A')}",
        'Latitude': ip_data.get('latitude', 'N/A'),
        'Longitude': ip_data.get('longitude', 'N/A'),
        'Timezone': ip_data.get('timezone', 'N/A'),
        'Current Time': datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S"),
        'ISP': ip_data.get('org', 'N/A'),
        'Organization': ip_data.get('org', 'N/A'),
        'Autonomous System': ip_data.get('asn', 'N/A'),
        'Platform Name': platform.system(),
        'System Languages': ', '.join(platform.architecture()),
        'Screen Width': screen_width,
        'Screen Height': screen_height,
        'Window Width': screen_width,
        'Window Height': screen_height,
        'CPU Threads': psutil.cpu_count(),
        'Available Browser Memory': f"{psutil.virtual_memory().available // (1024 ** 2)} MB"
    }
    return info

# Reproducción del video con inversión cuando llegue al final
def play_video(screen):
    video_clip = mp.VideoFileClip('video.mp4')
    reverse = False  # Controla si el video se reproduce al revés
    rotate_angle = 0

    while True:
        if reverse:
            video_clip = video_clip.fx(mp.vfx.time_mirror)  # Invertir video
        
        for frame in video_clip.iter_frames(fps=24, dtype="uint8"):
            rotate_angle = (rotate_angle + 2) % 360  # Girar el video 360 grados
            frame_surface = pygame.surfarray.make_surface(frame.swapaxes(0, 1))
            frame_surface = pygame.transform.rotate(frame_surface, rotate_angle)
            frame_surface = pygame.transform.scale(frame_surface, (screen_width, screen_height))
            
            screen.blit(frame_surface, (0, 0))
            pygame.display.update()
        
        reverse = not reverse  # Cambiar dirección después de cada ciclo

# Mostrar gradualmente la información con ajuste de tamaño
def display_information(screen, info):
    y_offset = 100  # Comienza un poco más abajo
    line_delay = 1  # Tiempo entre líneas

    for key, value in info.items():
        text = f"{key}: {value}"
        text_surface = font.render(text, True, WHITE)
        
        # Ajustar el tamaño del texto si no cabe en la pantalla
        while text_surface.get_width() > screen_width or (y_offset + text_surface.get_height()) > screen_height:
            global font_size
            font_size -= 2  # Reducir el tamaño de la fuente
            font = pygame.font.Font(None, font_size)
            text_surface = font.render(text, True, WHITE)

        screen.blit(text_surface, ((screen_width - text_surface.get_width()) // 2, y_offset))
        pygame.display.update()
        y_offset += text_surface.get_height() + 5  # Ajustar espacio entre líneas
        time.sleep(line_delay)

# Bucle principal
def main():
    running = True
    clock = pygame.time.Clock()
    
    # Fondo negro
    screen.fill(BLACK)

    # Obtener la información del sistema
    info = get_system_info()

    # Iniciar la reproducción del video en segundo plano
    video_thread = Thread(target=play_video, args=(screen,))
    video_thread.start()

    # Mostrar la información gradualmente
    display_information(screen, info)
    
    while running:
        for event in pygame.event.get():
            if event.type == pygame.QUIT or (event.type == pygame.KEYDOWN and event.key == pygame.K_ESCAPE):
                running = False

        clock.tick(30)
    
    pygame.quit()

if __name__ == "__main__":
    main()
