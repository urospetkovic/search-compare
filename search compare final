import random
import time


#  random guess (between updated x and y)
def guess_rand(x, y, num):
    run = True
    counter = 0
    while run is True:
        guess = random.randint(x, y)
        counter += 1
        if guess > num:
            y = guess-1
            guess = random.randint(x, y)
        elif guess < num:
            x = guess+1
            guess = random.randint(x, y)
        elif guess == num:
            run = False
    return counter


#  binary guess (middle between x and y)
def guess_binary(x, y, num):
    counter = 0
    run = True
    while run is True:
        guess = int((x + y) / 2)
        counter += 1
        if guess < num:
            x = guess+1
        elif guess > num:
            y = guess-1
        elif guess == num:
            run = False
    return counter


# guess binary recursive
def binary_recursive_search(x, y, num, counter):
    guess = int((x + y) / 2)
    counter += 1
    if guess < num:
        x = guess+1
        return binary_recursive_search(x, y, num, counter)
    elif guess > num:
        y = guess-1
        return binary_recursive_search(x, y, num, counter)
    if guess == num:
        return counter


numbers_range = 10000  # range of numbers to guess from
repetitions = 10000  # repeat

# list of numbers to guess
num_list = []
for i in range(int(repetitions)):
    num = random.randint(0, numbers_range)
    num_list.append(num)

# random guess loop
guesses_rand = []
start = time.time()
for i in range(int(repetitions)):
    guesses_rand.append(guess_rand(0, numbers_range, num_list[i]))
average_guesses_rand = float(sum(guesses_rand) / len(guesses_rand)).__round__(3)
end = time.time()
time_elapsed = float(end - start).__round__(3)
print('Average guesses random search:          ', average_guesses_rand)
print('Time elapsed:', time_elapsed, '\n')

# binary guess loop
guesses_binary = []
start = time.time()
for i in range(int(repetitions)):
    guesses_binary.append(guess_binary(0, numbers_range, num_list[i]))

average_guesses_binary = float(sum(guesses_binary) / len(guesses_binary)).__round__(3)
end = time.time()
time_elapsed = float(end - start).__round__(3)

print('Average guesses binary search:          ', average_guesses_binary)
print('Time elapsed:', time_elapsed, '\n')

# binary recursive guess loop
guesses_bin_rec = []
start = time.time()
for i in range(int(repetitions)):
    guesses_bin_rec.append(binary_recursive_search(0, numbers_range, num_list[i], 0))
avrg_bin_rec = float(sum(guesses_bin_rec) / len(guesses_bin_rec)).__round__(3)
end = time.time()
time_elapsed = float(end - start).__round__(3)
print('Average guesses binary recursive search:', avrg_bin_rec)
print('Time elapsed:', time_elapsed, '\n')

#  ratio between random and binary
ratio = float(average_guesses_rand / average_guesses_binary).__round__(2)
print('Ratio:  ', ratio, ': 1')
