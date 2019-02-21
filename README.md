def raca(c):
    if c == 1:
        rc.append("ELFO")
    elif c == 2:
        rc.append("HOBBIT")
    elif c == 3:
        rc.append("DRÍADE")
    elif c == 4:
        rc.append("GOBLIN")
    elif c == 5:
        rc.append("GIGANTE")
    elif c == 6:
        rc.append("HUMANO")
    elif c == 7:
        rc.append("TROLL DA MONTANHA")
    elif c == 8:
        rc.append("ORC")
    else:
        rc.append("ANÃO")
    return "Aguarde os resultados!"
def dados(n,c,p,cl):
    if c == 1:
        raca = "ELFO"
    elif c == 2:
        raca = "HOBBIT"
    elif c == 3:
        raca = "DRÍADE"
    elif c == 4:
        raca = "GOBLIN"
    elif c == 5:
        raca = "GIGANTE"
    elif c == 6:
        raca = "HUMANO"
    elif c == 7:
        raca = "TROLL DA MOTANHA"
    elif c == 8:
        raca = "ORC"
    elif c == 9:
        raca = "ANÃO"
    if cl == 1:
        classe = "ARQUEIRO"
    elif cl == 2:
        classe = "GUERREIRO"
    usuario = [n,p,raca,classe]
    MatrizTotal.append(usuario)
    return "\nObrigado pela participação!"
def resultado(ct,rc):
    print("A quantidade de inscritos no total foram:", ct)
    print("\nA quantidade de  ELFOS inscritos foram:", rc.count("ELFO"))
    print("A quantidade de  HOBBITS inscritos foram:", rc.count("HOBBIT"))
    print("A quantidade de  DRÍADES inscritos foram:", rc.count("DRÍADE"))
    print("A quantidade de  GOBLINS inscritos foram:", rc.count("GOBLIN"))
    print("A quantidade de  GIGANTES inscritos foram:", rc.count("GIGANTE"))
    print("A quantidade de  TROLLS DA MONTANHA inscritos foram:", rc.count("TROLL DA MONTANHA"))
    print("A quantidade de  ORCS inscritos foram:", rc.count("ORC"))
    print("A quantidade de  ANÃOS inscritos foram:", rc.count("ANÃO"))
    print("A quantidade de  HUMANOS inscritos foram:", rc.count("HUMANO"))
    return ""
#########################################################################################################################
def ordenação(MatrizTotal):
    for i in range(len(MatrizTotal)):
        posicaoMenor = i
        for j in range(i + 1, len(MatrizTotal)):
            if MatrizTotal[j] < MatrizTotal[posicaoMenor]:
                posicaoMenor = j
        if posicaoMenor != i:
            MatrizTotal[posicaoMenor], MatrizTotal[i] = MatrizTotal[i], MatrizTotal[posicaoMenor]
    MatrizTotal.reverse()
    x = 0
    while x < len(MatrizTotal):
        print("nome: %s, Pontuação: %d, Raça: %s, Classe: %s." % (MatrizTotal[x][0], MatrizTotal[x][1], MatrizTotal[x][2],MatrizTotal[x][3]))
        x = x + 1
    print("\nMelhor Guerreiro - Nome: %s, Pontuação: %d, Raça: %s, Classe: %s" % (
    MatrizTotal[0][0], MatrizTotal[0][1], MatrizTotal[0][2], MatrizTotal[0][3]))
    print("Pior Guerreiro - Nome: %s, Pontuação: %d, Raça: %s, Classe: %s" % (
        MatrizTotal[len(MatrizTotal)-1][0], MatrizTotal[len(MatrizTotal)-1][1], MatrizTotal[len(MatrizTotal)-1][2], MatrizTotal[len(MatrizTotal)-1][3]))
    return ""
########################################################################################################################
ct = 0 #contador
rc = []
MatrizTotal = []
while (ct >= 0):
    ct = ct + 1
    print("\n☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯\n"
          "☯  Welcome to the selection of warriors! ☯\n"
          "☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯☯")
    n = input("\nPor favor, digite seu nome: ")
    print("\n{}, indique sua raça:".format(n))
    c = int(input("\n(1)ELFO\t (2)HOBBIT\t (3)DRÍADE\t (4)GOBLIN\t (5)GIGANTE "
                  "(6)HUMANO\n\n(7)TROLL DA MOTANHA\t (8) ORC\t (9)ANÃO\n "
                  "\nSua opção: "))
    while (c < 1 or c > 9):
        print("\nDigite apenas os números indicados de 1 à 9")
        c = int(input("\n(1)ELFO\t (2)HOBBIT\t (3)DRÍADE\t (4)GOBLIN\t (5)GIGANTE "
                      "(6)HUMANO\n\n(7)TROLL DA MOTANHA\t (8) ORC\t (9)ANÃO\n "
                      "\nSua opção: "))
    print("\nContinue o seu registro.\nPara responder as perguntas a seguir digite (1) para SIM e (2) para NÃO")
    d = int(input("\nPossui todos os dentes inteiros? "))
    p = 0
    if (d == 1):
        p = p + 3
    while (d != 1 and d != 2):
        print("\nDigite apenas 1 ou 2!")
        d = int(input("\nPossui todos os dentes inteiros? "))
    g = int(input("\nJá lutou em alguma guerra? "))
    if (g == 1):
        p = p + 1
    while (g != 1 and g != 2):
        print("\nDigite apenas 1 ou 2!")
        g = int(input("Já lutou em alguma guerra? "))
    f = int(input("\nVocê é filho único? "))
    if (f == 1):
        p = p + 2
    while (f != 1 and f != 2):
        print("\nDigite apenas 1 ou 2!")
        f = int(input("Você é filho único? "))
    ar = int(input("\nPossui armadura própria? "))
    if (ar == 1):
        p = p + 1
    while (ar != 1 and ar != 2):
        print("\nDigite apenas 1 ou 2!")
        ar = int(input("Possui armadura própria? "))
    i = int(input("\nVocê foi indicado por algum nobre? "))
    if (i == 1):
        p = p + 2
        print("Não esqueça de apresentar o brasão do nobre para confirmar sua indicação!")
    while (i != 1 and i != 2):
        print("\nDigite apenas 1 ou 2!")
        i = int(input("Você foi indicado por algum nobre? "))
    print("\n{}, Indique sua clasificação: ".format(n))
    cl = int(input("\n(1) ➹ ARQUEIRO ➹\t (2) ♠ GUERREIRO ♠ \n"
                   "\nSua opção: "))
    while (cl != 1 and cl != 2):
            print("Digite apenas 1 ou 2!")
            cl = int(input("\n(1)➹ ARQUEIRO ➹\t (2) ♠ GUERREIRO ♠ \n"
                           "\nSua opção: "))
    if (cl == 1):
        pvfa = int(input("\nArqueiro, quantos acertos você fez? "))
        while (pvfa < 0 or pvfa > 20):
            print("\nValor inválido, a quantidade de acertos vão de 0 á 20!")
            pvfa = int(input("Arqueiro, quantos acertos você fez? "))
        p = p + pvfa
    if (cl == 2):
        pvfg = int(input("\nGuerreiro, quantas cabeças você arrancou? "))
        while (pvfg < 0 or pvfg > 20):
            print("\nValor inválido, a quantidade de cabeças arrancadas vão de 0 á 20!")
            pvfg = int(input("Guerreiro, quantas cabeças você arrancou? "))
        p = p + pvfg
    print(dados(n,c,p,cl))
    print(raca(c))
    condição = int(input("\nDigite 2 para iniciar um novo o registro! "))
    while condição != 2 and condição !=00:
        print("Digite Apenas 2!")
        condição = int(input("\nDigite 2 para iniciar um novo registro!! "))
    ###################################################################
    #                    Senha Para Mostrar os Resultados             #
    ###################################################################
    if (condição == 00):
        print("\n\t\t **RESULTADOS**\n")
        print(ordenação(MatrizTotal))
        print(resultado(ct,rc))
        break
