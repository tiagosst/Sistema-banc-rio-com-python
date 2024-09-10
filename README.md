# Sistema-banc-rio-com-python
import textwrap
def menu():=...
    menu = """"\n
    ================ MENU ==================
    [d]\tDepositar
    [s]\tSacar
    [e]\tExtrato
    [nc]\tNova conta
    [lc]\tLista contas
    [nu]\tNovo usuario
    [q]\tSair
    => """
    return input(textwrap.dedent(menu))


def depositar(saldo, valor, extrato, /):...
        if valor > 0:
            saldo += valor
            extrato += f"Deposito:\tR$ {valor:.2f}\n"
            print("\n=== Deposito realizado com sucesso!===")
        else:
            print("\n@@@ operacao falhou! o valor informado é invalido. @@@") 

        return saldo, extrato



def sacar(*, saldo, valor, extrato, limite, numero_saque, limite_saque):...
    excedeu_saldo = valor > saldo
    excedeu_limite = valor > limite
    excedeu_saques = numro_saques > limites_saque

    if excedeu_saldo:
        print("\@@@ operacao falhou! você não tem saldo suficiente. @@@")

elif excedeu_limites
    print("\@@@ operção falhou!! o valor do saque excede o limite. @@@")

elif excedeu_saques
    print("\@@@ operação falhou!!  numero maximo de saques excedido. @@@")

elif valor > 0:
    saldo -= Valor
    extrato += f"saque:\t\R$ {valor:.2f}\n"
    numero_saques += 1
    print("\n=== Saque realizado com sucesso! ===")

else:
    print("\@@@ operação falhou! o valor informado é invalido. @@@")

return saldo, extrato

def exibir_extrato(saldo, /, *, extrato):...
    print("\n================ EXTRATO ================")
        print("Não foram realizadas movimentações." if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("==========================================")


def criar_usuario(usuarios):...
    cpf = input("Informe o CPF(somente o numero):")
    usuario = filtrar_usuario(cpf, usuarios)

    if usuario:
        print("\@@@ já existe usuario com esse cpf!! @@@")

        return
    
    nome = input("Informe o nome completo:")
    data_nascimento = input("Informe a data do nscimento (dd-mm-aaaa):")

    usuarios.append({"nome": nome, "data_nascimento": data_nascimento, "cpf": cpf, "endereço": endereço})
    print("=== Usuario criado com sucesso! ===")

def filtrar_usuario(cpf, usuarios):...
    usuarios_filtrados = [usuario for usuario in usuarios if usuario["cpf"] == cpf]
    return usuarios_filtrados[0] if usuarios_filtrados else None

def criar_conta(agencia, numero_conta, usuarios):...
    cpf = input("Informe o cpf do usuario:")
    usuario = filtrar_usuario(cpf, usuario)
if usuario:
    print("\n=== conta criada com sucesso!! ===")
    return{"agencia": agencia, "numero_conta": numero_conta, "usuario": usuario}
print("\@@@ usuario não encontrado, fluxo de criação de conta encerrado! @@@")


def listar_contas(contas):...
    for conta in contas:
        linha = f"""\
            agencia:\t{conta['agencia']}
            c\c:\t\t{conta['numero da conta']}
            titular:\t{conta['usuario']['nome']}
        """
        print("=" * 100)
        print(textwrap.dedent(linha))

def main():...
    LIMITE_SAQUES = 3
    AGENCIA = "0001"
    
    saldo = 0
    limite = 1000
    extrato =""
    numero_saque = 0
    usuarios = []
    contas = []

    while True:

        opcao = menu()

        if opcao == "d":
            valor = float(input("informe o valor do deposito: "))
            saldo, extrato = depositar(saldo=saldo, valor=valor, extrato=extrato)


        if opcao == "s":
            valor = float(input("informe o valor do saque:"))

            saldo, extrato = sacar(
                saldo=saldo,
                valor=valor,
                extrato=extrato,
                numero_saque=numero_saque,
                limite_saque=LIMITE_SAQUES,


            )



        elif opcao == "e"
    exibir_extrato(saldo, extrato=extrato)

        elif opcao == "nu":
    criar_usuario(usuarios)

        elif opcao == "nc"
    numero_conta = len(contas) + 1
    conta = criar_conta(AGENCIA, numero_conta, usuarios)

        if clonta:
    contas.append(conta)

        elif opcao  == "lc":
    listar_contas(contas)

elif opcao  =="q":
    break

else:
    print("Operacao invalida, por favor selecione novamente a operacao desejada.")


main()





