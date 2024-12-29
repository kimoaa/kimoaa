from mblock import event
@event.greenflag
def on_greenflag():
    word = []
    correct_guess = 0
    number = sprite.input('how may letters is the word')
    loss=0
    for i in range(number):
        letter = sprite.input('the letters')
        word.append (letter)
    
    for i in range(6):
        guess = sprite.input('what is your guess')
        if guess in word:
            sprite.say('correct',2)
            sprite.set_variable(correct_guess,+1)
            word.pop(guess)
        else:
            sprite.say('incorrect')
            sprite.set_variable(loss, +1)

    if correct_guess ==number:
            sprite.say('winner',  2)
