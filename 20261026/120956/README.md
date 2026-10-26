프로그래머스 120956 옹알이
백트래킹

```python

dic_words = {}

def make_word(string, words, check):
    if sum(check) == len(words):
        return
    for i in range(len(words)):
        if check[i] == 0:
            new = string + words[i]
            dic_words[new] = 1
            #print(new)
            check[i] = 1
            make_word(new, words, check)
            check[i] = 0

def solution(babbling):
    answer = 0
    words = ["aya", "ye", "woo", "ma"]
    check = [0, 0, 0, 0]
    
    make_word("",words, check)
    
    for w in babbling:
        if dic_words.get(w) != None:
            print(w)
            answer += 1
    return answer

```