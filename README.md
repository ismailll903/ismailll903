import pygame

pygame.init()

# Ekran ayarları
screen_width = 800
screen_height = 600
screen = pygame.display.set_mode((screen_width, screen_height))
pygame.display.set_caption("Roket Oyunu")

# Renkler
white = (255, 255, 255)
black = (0, 0, 0)

# Roket
rocket_img = pygame.image.load('rocket.png')
rocket_x = screen_width // 2
rocket_y = screen_height // 2

# Puan
score = 0
font = pygame.font.Font('freesansbold.ttf', 32)

# Oyun döngüsü
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        if event.type == pygame.MOUSEBUTTONDOWN:
            rocket_y -= 50

    # Ekranı temizle
    screen.fill(white)

    # Roket çiz
    screen.blit(rocket_img, (rocket_x, rocket_y))

    # Puanı göster
    score_text = font.render("Puan: " + str(score), True, black)
    screen.blit(score_text, (10, 10))

    # Ekranı güncelle
    pygame.display.update()

pygame.quit()
