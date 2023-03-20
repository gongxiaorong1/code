# codeimport random

def main():
    number_to_guess = random.randint(1, 100)
    tries = 0
    guessed = False

    print("猜一个1到100之间的整数。你有10次机会！")

    while not guessed and tries < 10:
        try:
            user_guess = int(input("请输入你猜的数字："))
        except ValueError:
            print("无效输入。请输入一个整数。")
            continue

        tries += 1

        if user_guess == number_to_guess:
            guessed = True
        elif user_guess < number_to_guess:
            print("猜低了！")
        else:
            print("猜高了！")

    if guessed:
        print(f"恭喜你！你在{tries}次尝试后猜对了数字{number_to_guess}！")
    else:
        print(f"很遗憾，你没有在10次内猜对。正确的数字是{number_to_guess}。")

if __name__ == "__main__":
    main()
