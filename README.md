def product_of_positive(arr):
    
    product = 1
    has_positive = False
    for x in arr:
        if x > 0:
            product *= x
            has_positive = True
    return product if has_positive else 0


def sum_before_min(arr):
    
    min_index = arr.index(min(arr))
    return sum(arr[:min_index])


def sort_even_odd_positions(arr):
   
    even = sorted(arr[1::2])  
    odd = sorted(arr[0::2])   

    result = []
    e = o = 0
    for i in range(len(arr)):
        if i % 2 == 0:
            result.append(odd[o])
            o += 1
        else:
            result.append(even[e])
            e += 1
    return result


def main():
    n = int(input("Введіть кількість елементів масиву: "))
    arr = []

    for i in range(n):
        arr.append(float(input(f"Введіть елемент {i + 1}: ")))

    prod = product_of_positive(arr)
    s = sum_before_min(arr)
    sorted_arr = sort_even_odd_positions(arr)

    print("\nПочатковий масив:", arr)
    print("Добуток додатних елементів:", prod)
    print("Сума елементів до мінімального:", s)
    print("Масив після впорядкування:", sorted_arr)


if __name__ == "__main__":
    main()
