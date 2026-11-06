import random

def jogo_adivinhacao():
    numero_secreto = random.randint(1, 100)
    tentativas = 0
    acertou = False
    
    print("=== JOGO DA ADIVINHAÇÃO ===")
    print("Tente adivinhar o número entre 1 e 100!\n")
    
    while not acertou:
        try:
            chute = int(input("Digite o seu palpite: "))
            tentativas += 1
            
            if chute < 1 or chute > 100:
                print("Por favor, digite um número entre 1 e 100.")
                continue
                
            if chute < numero_secreto:
                print("O número secreto é MAIOR ⬆️")
            elif chute > numero_secreto:
                print("O número secreto é MENOR ⬇️")
            else:
                acertou = True
                print(f"\n🎉 Parabéns! Você acertou o número {numero_secreto} em {tentativas} tentativa(s)!")
                
        except ValueError:
            print("Entrada inválida! Por favor, digite um número inteiro.")

# Executa o jogo
if __name__ == "__main__":
    jogo_adivinhacao()
