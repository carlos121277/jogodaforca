# jogodaforca
# JOGO DA FORCA EM PYTHON UTILIZANDO O PYGAME

import pygame as pg
import random

# Cores do jogo
branco = (255, 255, 255)
preto = (0, 0, 0)

# Setup da tela do Jogo
window = pg.display.set_mode((1000, 600))
display = pg.display.set_mode((1000,600))




# Inicializando fonte
pg.font.init()
# Escolhendo uma fonte e tamanho
fonte = pg.font.SysFont("Arial Black", 50)
fonte_rb = pg.font.SysFont("Arial Black", 30)

palavras = ['TECNOLOGIA',
            'PROGRAMACAO',
            'ALGORITMO',
            'FORCA','PYTHON','COMPUTACAO']


tentativas_de_letras = [' ', '-']
palavra_escolhida = ''
palavra_camuflada = ''
end_game = True
chance = 0
letra = ' '
click_last_status = False

def Sorteando_Palavra(palavras, palavra_escolhida, end_game):
    if end_game == True:
        palavra_n = random.randint(0, len(palavras) - 1)
        palavra_escolhida = palavras[palavra_n]
        print(palavra_escolhida)
        end_game = False
        chance
    return palavra_escolhida, end_game
def Desenho_da_Forca(window, chance):
    # Desenho da Forca
    pg.draw.rect(window, branco, (0, 0, 1000, 600))
    pg.draw.line(window, preto, (100, 500), (100, 100), 10)
    pg.draw.line(window, preto, (50, 500), (150, 500), 10)
    pg.draw.line(window, preto, (100, 100), (300, 100), 10)
    pg.draw.line(window, preto, (300, 100), (300, 150), 10)
    
    if palavra_escolhida == 'TECNOLOGIA':
        texto1 = fonte_rb.render('indispensavel', 1, preto)
        display.blit(texto1, (500,210))
    
    if chance == 1:
        # Cabeça
        pg.draw.circle(window, preto, (300, 200), 50, 10)
        texto1 = fonte_rb.render('Você tem 5 tentativas para acertar a palavra', 1, preto)
        display.blit(texto1, (150,40))
    if chance == 2:
        # Tronco
        pg.draw.circle(window, preto, (300, 200), 50, 10)
        pg.draw.line(window, preto, (300, 250), (300, 350), 10)
        texto1 = fonte_rb.render('Você tem 4 tentativas para acertar a palavra', 1, preto)
        display.blit(texto1, (150,40))
    if chance == 3:
        # Braço Direito
        pg.draw.circle(window, preto, (300, 200), 50, 10)
        pg.draw.line(window, preto, (300, 250), (300, 350), 10)
        pg.draw.line(window, preto, (300, 260), (225, 350), 10)
        texto1 = fonte_rb.render('Você tem 3 tentativas para acertar a palavra', 1, preto)
        display.blit(texto1, (150,40))
    if chance == 4:
        # Braço Esquerdo
        pg.draw.circle(window, preto, (300, 200), 50, 10)
        pg.draw.line(window, preto, (300, 250), (300, 350), 10)
        pg.draw.line(window, preto, (300, 260), (225, 350), 10)
        pg.draw.line(window, preto, (300, 260), (375, 350), 10)
        texto1 = fonte_rb.render('Você tem 2 tentativas para acertar a palavra', 1, preto)
        display.blit(texto1, (150,40))
    if chance == 5:
        # Perna Direita
        pg.draw.circle(window, preto, (300, 200), 50, 10)
        pg.draw.line(window, preto, (300, 250), (300, 350), 10)
        pg.draw.line(window, preto, (300, 260), (225, 350), 10)
        pg.draw.line(window, preto, (300, 260), (375, 350), 10)
        pg.draw.line(window, preto, (300, 350), (375, 450), 10)
        texto1 = fonte_rb.render('Você tem 1 tentativas para acertar a palavra', 1, preto)
        display.blit(texto1, (150,40))
    if chance == 6:
        # Perna Direita
        pg.draw.circle(window, preto, (300, 200), 50, 10)
        pg.draw.line(window, preto, (300, 250), (300, 350), 10)
        pg.draw.line(window, preto, (300, 260), (225, 350), 10)
        pg.draw.line(window, preto, (300, 260), (375, 350), 10)
        pg.draw.line(window, preto, (300, 350), (375, 450), 10)
        pg.draw.line(window, preto, (300, 350), (225, 450), 10)
        if palavra_escolhida == 'TECNOLOGIA':
            texto1 = fonte_rb.render('Você perdeu! :(', 1, preto)
            display.blit(texto1, (570, 200))
            texto1 = fonte_rb.render('É INDISPENSAVEL NO NOSSO DIA A DIA', 1,preto)
            display.blit(texto1, (580,300))
            texto1 = fonte_rb.render('A palavra era TECNOLOGIA', 1, preto)
            display.blit(texto1, (470, 270))
        
        if palavra_escolhida == 'PROGRAMACAO':
            texto1 = fonte_rb.render('Você perdeu! :(', 1, preto)
            display.blit(texto1, (570, 200))
            texto1 = fonte_rb.render('A palavra era PROGRAMAÇÃO', 1, preto)
            display.blit(texto1, (470, 270))
        
        if palavra_escolhida == 'ALGORITMO':
            texto1 = fonte_rb.render('Você perdeu! :(', 1, preto)
            display.blit(texto1, (570, 200))
            texto1 = fonte_rb.render('A palavra era ALGORITMO', 1, preto)
            display.blit(texto1, (470, 270))
        
        if palavra_escolhida == 'FORCA':
            texto1 = fonte_rb.render('Você perdeu! :(', 1, preto)
            display.blit(texto1, (570, 200))
            texto1 = fonte_rb.render('A palavra era FORCA', 1, preto)
            display.blit(texto1, (470, 270))
        
        if palavra_escolhida == 'PYTHON':
            texto1 = fonte_rb.render('Você perdeu! :(', 1, preto)
            display.blit(texto1, (570, 200))
            texto1 = fonte_rb.render('A palavra era PYTHON', 1, preto)
            display.blit(texto1, (470, 270))
        
        if palavra_escolhida == 'COMPUTACAO':
            texto1 = fonte_rb.render('Você perdeu! :(', 1, preto)
            display.blit(texto1, (570, 200))
            texto1 = fonte_rb.render('A palavra era COMPUTAÇÃO', 1, preto)
            display.blit(texto1, (470, 270))



def Desenho_Restart_Button(window):
    pg.draw.rect(window, preto, (700, 100, 200, 65))
    texto = fonte_rb.render('Restart', 1, branco)
    window.blit(texto, (740, 110))
    


def Camuflando_Palavra(palavra_escolhida, palavra_camuflada, tentativas_de_letras):
    palavra_camuflada = palavra_escolhida
    for n in range(len(palavra_camuflada)):
        if palavra_camuflada[n:n + 1] not in tentativas_de_letras:
            palavra_camuflada = palavra_camuflada.replace(palavra_camuflada[n], '#')
    return palavra_camuflada

def Tentando_uma_Letra(tentativas_de_letras, palavra_escolhida, letra, chance):
    if letra not in tentativas_de_letras:
        tentativas_de_letras.append(letra)
        if letra not in palavra_escolhida:
            chance += 1
        
    elif letra in tentativas_de_letras:
        pass
    
    return tentativas_de_letras, chance

def Palavra_do_Jogo(window, palavra_camuflada):
    palavra = fonte.render(palavra_camuflada, 1, preto)
    window.blit(palavra, (200, 500))

#def exibe_mensagem(display):
    #texto1 = fonte_rb.render('Game Over! Click no botão restart para reiniciar o jogo', 1, preto)
    #display.blit(texto1, (250, 300))
    

#game_over = exibe_mensagem(display)
def Restart_do_Jogo(palavra_camuflada, end_game, chance, letra, tentativas_de_letras, click_last_status, click, x, y):
    count = 0
    limite = len(palavra_camuflada)
    for n in range(len(palavra_camuflada)):
        if palavra_camuflada[n] != '#':
            count += 1
    if count == limite:
        texto1 = fonte_rb.render('Parabéns, você venceu! :)', 1, preto)
        display.blit(texto1, (450, 330))
        
    if click_last_status == False and click[0] == True:
        print('Ok')
        
        if x >= 700 and x <= 900 and y >= 100 and y <= 165:
            
            tentativas_de_letras = [' ', '-']
            end_game = True
            chance = 0
            letra = ' '
            
    return end_game, chance, tentativas_de_letras, letra

def jogo(window):
        
        window.fill('yellow')
        global chance
        global palavra_escolhida
        global end_game
        global palavra_camuflada
        global tentativas_de_letras
        global letra
        Desenho_da_Forca(window, chance)
        Desenho_Restart_Button(window)
        palavra_escolhida, end_game = Sorteando_Palavra(palavras, palavra_escolhida, end_game)
        palavra_camuflada = Camuflando_Palavra(palavra_escolhida, palavra_camuflada, tentativas_de_letras)
        tentativas_de_letras, chance = Tentando_uma_Letra(tentativas_de_letras, palavra_escolhida, letra, chance)
        Palavra_do_Jogo(window, palavra_camuflada)
        end_game, chance, tentativas_de_letras, letra= Restart_do_Jogo(palavra_camuflada, end_game, chance, letra, tentativas_de_letras, click_last_status, click, mouse_position_x, mouse_position_y)
        
def telainicial(display):
        
        teste = True
        while teste:
            for event2 in pg.event.get():
                if event2.type == pg.QUIT:
                    pg.quit()
                    quit()    

        
        
                display.fill('blue')
                texto2 = fonte_rb.render('Pressione uma tecla para jogar', 1, branco)
                display.blit(texto2, (250, 330))
                texto1 = fonte_rb.render('Bem vindo ao jogo da forca da AUTECH!', 1, branco)
                display.blit(texto1, (200, 200))
                texto1 = fonte_rb.render('Você tem 6 tentativas para acertar a palavra', 1, branco)
                display.blit(texto1, (150, 270))
            
            
                if(event2.type == pg.KEYUP):
                    teste = False
                    
                    

                    
                    
            pg.display.flip()


telainicial(window)
while True:
    
    for event in pg.event.get():
        if event.type == pg.QUIT:
            pg.quit()
            quit()
        if event.type == pg.KEYDOWN:
            letra = str(pg.key.name(event.key)).upper()

    # Declarando variavel da posição do mouse
    mouse = pg.mouse.get_pos()
    mouse_position_x = mouse[0]
    mouse_position_y = mouse[1]

    # Declarando variavel do click do mouse
    click = pg.mouse.get_pressed()

    #Jogo
    jogo(display)
    
    
    #Click Last Status
    if click[0] == True:
       click_last_status = True
    #else:
       click_last_status = False
    
    
    pg.display.update()
