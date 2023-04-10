# Sistema-Bancario-em-Python-

Menu = """
[1] Deposito
[2] Sacar
[3] Extrado 
[4] Sair do sistema 
=> """

saldo = 0 
deposito = 0 
limite = 500 
extrato = ""
numero_Saques = 0 
limites_Saques = 3 
opcao = ""

while True:
    opcao = input(Menu)
    
    if opcao == "1":
        deposito = float(input('Quanto deseja Depositar? R$'))

        if deposito > 0:
            saldo = saldo + deposito 
            print(f'saldo: R${saldo}')
            extrato += (f'\nDeposito: R$ {deposito:.2f}')
        else:
            print('Operação falhou ! Digite um valor válido!')
            break 
    elif opcao == "2":
        while True:
            if numero_Saques >= limites_Saques:
                print("Foi realizando o Limite máximo de saques permitidos por dia")
                break
            saque = float(input("Qual valor deseja Sacar ? R$"))
            if saque > saldo : 
                print("Não foi possivel sacar esse valor! sem saldo suficiente.")
                break
            if saque >= 500:
                print("Saque acima do permitido de R$500,00 reais diario")
                break 
            if saque > 0 :
                if saque > 0 and deposito == 0:
                    break
                else:
                    saldo = saldo - saque 
                    extrato += (f'\nsaque: R$ -{saque}')
                    print(f'Saldo: R${saldo}')
                    numero_Saques += 1 
                    break
            else:
                print("valor Informado inválido !")
    elif opcao == "3":
        print("===============EXTRADO=============") 
        print("Não ouvi movimentação em sua conta." if not extrato else extrato)
        print(f'Saldo: R$ {saldo:.2f}')
        print("===================================")
    elif opcao == "4":
        print("saindoo...")
        break 
    else:
        print("operação inválida , por favor digite uma opção valida!")
