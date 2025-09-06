# Cartas-Super-trunfo
class Carta:
    def __init__(self, nome, poder, velocidade, força):
        self.nome = nome
        self.poder = poder
        self.velocidade = velocidade
        self.força = força

    def __str__(self):
        return f"{self.nome} - Poder: {self.poder}, Velocidade: {self.velocidade}, Força: {self.força}"

class Jogo:
    def __init__(self):
        self.cartas = [
            Carta("Super-Homem", 10, 8, 9),
            Carta("Flash", 7, 10, 6),
            Carta("Thor", 9, 7, 10),
            Carta("Batman", 8, 6, 9),
            Carta("Spider-Man", 7, 8, 7)
        ]

    def comparar_cartas(self, carta1, carta2):
        if carta1.poder > carta2.poder:
            return carta1.nome
        elif carta2.poder > carta1.poder:
            return carta2.nome
        else:
            return "Empate"

    def jogar(self):
        print("Bem-vindo ao Jogo de Cartas Super Trunfo!")
        print("As cartas disponíveis são:")
        for carta in self.cartas:
            print(carta)
        print("\nVamos jogar!")
        carta1 = input("Escolha a primeira carta (digite o nome): ")
        carta2 = input("Escolha a segunda carta (digite o nome): ")

        carta1 = next((c for c in self.cartas if c.nome == carta1), None)
        carta2 = next((c for c in self.cartas if c.nome == carta2), None)

        if carta1 and carta2:
            vencedor = self.comparar_cartas(carta1, carta2)
            print(f"O vencedor é: {vencedor}!")
        else:
            print("Carta não encontrada.")

# Iniciar o jogo
jogo = Jogo()
jogo.jogar()
