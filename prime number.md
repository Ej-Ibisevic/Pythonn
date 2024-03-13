
def is_prime(n):
    if n <= 1:
        return False
    if n <= 3:
        return True
    if n % 2 == 0 or n % 3 == 0:
        return False
    i = 5
    while i * i <= n:
        if n % i == 0 or n % (i + 2) == 0:
            return False
        i += 6
    return True

def display_primes():
    print("Prime numbers between 1 and 250:")
    for num in range(1, 251):
        if is_prime(num):
            print(num, end=" ")

display_primes()

def write_primes_to_file():
    with open("results.txt", "w") as file:
        file.write("Prime numbers between 1 and 250:\n")
        for num in range(1, 251):
            if is_prime(num):
                file.write(str(num) + " ")

write_primes_to_file()
