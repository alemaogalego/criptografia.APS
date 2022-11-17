import random
#Importa a biblioteca "random" para pegar valores aleatórios

def rand(min, max):
    #Função que gera um valor aleatório para inserir em posições aleatórias
    return int((max - min) * random.random() + min)
    #Retorna um valor aleatório que esteja dentro do tamanho da tabela


def gerar_tabela():
    #Função que cria a tabela onde os caracteres se encontrarão em posições aleatórias
    alfabeto = []
    #Cria uma array vazia, onde será adicionado cada valor da tabela ASCII
    for i in range(0, 257):
        #Um for que adiciona 256 valores de 0 a 256
        alfabeto.append(chr(i))
        #Cada valor de i é então adicionado na lista e traduzido para um caractere da tabela ASCII
    alfabeto = "".join(alfabeto)
    #De lista o "alfabeto" vira uma string juntando tudo sem espaços
    tabela = [[0] * 16 for fileira in range(16)]
    #Cria uma tabela de 16x16 vazia(com zeros) onde serão inseridos os caracteres da tabela ASCII
    for y in range(16):
        #Um for que diz para passar pelas 16 linhas da tabela
        for x in range(16):
            #Um for que diz para passar pelas 16 colunas da tabela
            tabela[x][y] = alfabeto[rand(0, len(alfabeto))]
            #Diz que cada valor(antes 0) da tabela agora receberá um valor novo
            #Chamando então a função que "rand" que randomizará as posições dos elementos na tabela
            alfabeto = alfabeto.replace(tabela[x][y], '')
            #Altera a posição dos valores
    return tabela
    #Retorna a tabela que esta com todos os caracteres da tabela ASCII(será a chave!)


def gerarString(x, formato='%02s'):
    #Função que gera os indices da tabela
    return ' '.join(formato % i for i in x)
    #Adiciona os valores de I como indice de X quando a tabela for escrita


def mostrartabela(tabela):
    #função que faz a tabela ser escrita
    print(' ' + gerarString(range(1, 17)))
    #Escreve então os indices, chamando a função que aplica os indices de X(coluna)
    for fileira in range(0, len(tabela)):
        #For que repetirá por 16 vezes(até o tamanho da tabela) para gerar todas as linhas(Y)
        print(str(fileira + 1) + gerarString(tabela[fileira]))
        #Print para escrever todas as linhas(Y) da tabela


def encrypt(tabela, palavras):
    #Função para codificar que recebe a tabela e a mensagem a ser codificada
    string = tabela
    #Variavel string recebe a tabela
    cipher = ''
    #Variavel que irá dar a mensagem codificada
    for ch in palavras:
        #For que irá olhar todos os caracteres da mensagem um por um
        for fileira in range(len(tabela)):
            #For que irá olhar coluna por coluna e para cada elemeno que estiver em tal coluna...
            if ch in tabela[fileira]:
                #Irá então encontrar a linha de onde se encontra o caractere na tabela
                x = str((tabela[fileira].index(ch) + 1)).zfill(2)
                #Variavel de coordenada que receberá a coluna que o caractere se encontra
                y = str(fileira + 1).zfill(2)
                #Variavel de coordenada que receberá a linha que o caractere se encontra
                cipher += y + x
                #Cipher será a coordenada completa(linha e coluna) de cada caractere, recebendo então
                #A posição de todos os digitos da mensagem
    return cipher
    #Retorna a coordenada


def decrypt(tabela, numeros):
    #Função para decriptar
    #Recebe a chave(a tabela) e a mensagem criptografada(que são todas as coordenadas juntas)
    texto = ''
    #Variavel que receberá a mensagem descodificada
    for index in range(0, len(numeros), 2):
        #Um for que vai pegar até o final das coordenadas dadas
        chunks = [numeros[i:i+4] for i in range(0, len(numeros), 4)]
        #Separa as coordenadas que estavam juntas de cada digito, como cada caractere é definido por
        #4 digitos de coordenada, separa de 4 em 4 elementos
        #Sendo os dois primeiros sua coordenada Y(linha) e os dois últimos o X(coluna)
    for i in range(0, len(chunks)):
        #Pega então cada coordenada de cada caractere separadamente que foi divido
        y = int(chunks[i][0] + chunks[i][1])
        #Os dois primeiros de cada partição então equivalem a linha que se encontra na tabela
        x = int(chunks[i][2] + chunks[i][3])
        #Os dois últimos de cada partição então equivalem a coluna que se encontra na tabela
        texto += tabela[y - 1][x - 1]
        #"Texto" receberá a tradução, recebendo então o valor da "tabela" da coordenada recebida
        #de cada caractere
    return texto
    #Retorna a mensagem decriptada


if __name__ == '__main__':
    #Função que coloca os "-------" para ficar bonitinho na hora de mostra a tabela
    tabela = gerar_tabela()
    print('-' * 19)
    #"Apenas diz a quantidade de traços e as escreve"
    mostrartabela(tabela)
    print('-' * 19)
    #"Apenas diz a quantidade de traços e as escreve"
    ciphertext = encrypt(tabela, "Maça e banana!")
    #Variável que receberá a mensagem a ser encriptada
print(f'Aqui está o seu arquivo encriptado: {ciphertext}')
#Chama a função para encripta a mensagem digitada na "ciphertext"
print(f'Aqui está o seu arquivo decriptado: {decrypt(tabela, ciphertext)}')
#Chama a função para decifrar utilizando a tabela como chave e a variavel que possui a mensagem encriptada
#E então escreve a mensagem como era antes
