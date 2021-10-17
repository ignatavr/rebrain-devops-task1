#Seed Recovery Script

seed-recovery-scrypt - позволяет вам подобрать нужную мнемоническую фразу биткоин кошелька, 
если вы не знаете нужную последовательность ключевых сраз.

*Казалось бы задача звучит тривиально однако при наличии 12 слов в мнемоники вам необходимо проверить*
**499 млн вариантов**

##Seed Recovery Script
применим для следующих bip:
1. bip32
2. bip44
2. bip49
3. bip84

***Кроме того SRS применим для следующих криптовалют***
- Bitcoin
- Etherium
- Bitcoin Cash
- и другие

Для создания валидной mnemici необходимо воспользоваться [Mnemonic Code Converter](https://iancoleman.io/bip39/)

![iancoleman logo](https://callisto.network/wp-content/uploads/2021/05/2021-05-21_03h22_41.jpg)

Ниже в таблице представлены заголовки адресов биткоин кошельков в соответствии с реализацией различных BIP

bip32 | bip 44 | bip 49 | bip 84
----- | ------ | ------ | ------
1LJBn | 1DgiM  | 35aek5 | bc1qnv 

На основании протокола реализации валидной мнемонической фразы из 128-битнлй последдовательности
последняя слово в мнемоники является контрольной суммой всей мнемонической фразы, данное условие
сокращает количество подходящих вариантов примерно в 16 раз

```
import itertools
from cryptotools.BTC import Xprv

wordlist = []
for i in range (0, 3):
    newWord = input(f'Plese, enter word number {i+1}!')
    wordlist.append(newWord)
    #word1 = input('Plese, enter 1st word!')
    #word2 = input('Plese, enter 1st word!')
    #word3 = input('Plese, enter 1st word!')

perm_set = itertools.permutations(wordlist)

for i in perm_set:
    #m = Xprv.from_mnemonic(f'add april today divide stage divorce frequent fine melody movie town marriage')
    #print(type(i))
    sttr = ' '.join(i)



def seedCorrect(seedPhrazes):
    with m = Xprv.from_mnemonic(f'{seedPhrazes}') as seedCorrect:
        try:
            print((m/0/0).address('P2PKH'))
            print(seedPhrazes)

        except InvalidMnemonic
```

> «Держитесь от них подальше. По своей сути это мираж. 
О криптовалютах можно с определенностью сказать, что конец их будет плохим»
> - Уоррен Баффетт, глава Berkshire Hathaway
