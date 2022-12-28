import random

num_dig = 3
max_guesses = 10

def main():
    print('''Bajgle, logiczna gra na dedukcję.
Mam na myśli 3 cyfrową liczbę, w której żadna z cyfr się nie powtarza.
Spróbuj ją odgadnąć, tutaj pare wskazówek:
Gdy mówię:      Oznacza to:
Piko            Jedna cyfra jest poprawna, ale jest na złej pozycji.
Fermi           Jedna cyfra jest poprawna i znajduję się na dobrej pozycji.
Bajgle          Żadna z cyfr nie jest poprawna.

Na przykład, jeśli liczba to 123, a Ty podasz liczbę 325, wskazówka pokaże: Fermi Piko.'''.format(num_dig))

    while True:
        secretNum = getSecretNum()
        print('Mam na myśli liczbę.')
        print('Spróbuj zgadnąć jaka to liczba, masz 10 prób.'.format(max_guesses))

        numGuesses = 1
        while numGuesses <= max_guesses:
            guess = ''
            while len(guess) != num_dig or not guess.isdecimal():
                print('Próba: '.format(numGuesses))
                guess = input('> ')

            clues = getClues(guess, secretNum)
            print(clues)
            numGuesses += 1

            if guess == secretNum:
                break
                if numGuesses > max_guesses:
                    print('Wykorzystałeś wszystkie próby.')
                    print('Prawidłowa odpowiedź to: {}.'.format(secretNum))

        print('Czy chcesz grać ponownie ? (tak/nie)')
        if not input('> ').lower().startswith('tak'):
            break
    print('Dziękuję za grę !')

def getSecretNum():
    numbers = list('0123456789')
    random.shuffle(numbers)

    secretNum = ''
    for i in range(num_dig):
        secretNum += str(numbers[i])
    return secretNum

def getClues(guess, secretNum):
    if guess == secretNum:
        return 'Udało się, Gratulacje !!!'

    clues = []

    for i in range(len(guess)):
        if guess[i] == secretNum[i]:
            clues.append('Fermi')
        elif guess[i] in secretNum:
            clues.append('Piko')
    if len(clues) == 0:
        return 'Bajgle'
    else:
        clues.sort()
        return ' '.join(clues)

if __name__ == '__main__':
    main()
