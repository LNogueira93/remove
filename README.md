def remover():
    lista = []
    print("Remover um contato")
    with open("agendatelefonica.csv") as agenda:
        reader = csv.reader(agenda)
        for linha in reader:
            lista.append(linha)
        nome = input('Nome: ')
        if nome in lista:
            sn = input('Excluir {}? (s/n): '.format(nome))
            if sn == 's':
                lista.pop(0)
                agenda = open('agendatelefonica.csv', 'w')
                for x in lista:
                    agenda.write(', '.join(x) + '\n')
                    print('Contato removido com sucesso!\n')
