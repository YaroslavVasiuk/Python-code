def sort_special(arr):
    positives = sorted([x for x in arr if x > 0])
    negatives = sorted([x for x in arr if x < 0], reverse=True)
    zeros = [x for x in arr if x == 0]
    return positives + zeros + negatives

a = list(map(int, input("Введіть елементи першого масиву: ").split()))
b = list(map(int, input("Введіть елементи другого масиву: ").split()))

diff_count = len(set(a).symmetric_difference(set(b)))
print("Кількість неоднакових елементів:", diff_count)

a = [x if x in b else 0 for x in a]

a_sorted = sort_special(a)
b_sorted = sort_special(b)

print("Перший масив після обробки:", a_sorted)
print("Другий масив після сортування:", b_sorted) 
