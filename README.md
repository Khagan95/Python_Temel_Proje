# Python_Temel_Proje
"""
Proje 1 ve Proje 2 
hem listeyi düzleştiren (flatten) fonksiyonu, hem de iç içe listeleri tersine çeviren fonksiyonu Python ile tanımladım
"""
#Proje 1. Listeyi düzleştiren (flatten) fonksiyon
def flatten(lst):
    result = []
    for item in lst:
        if isinstance(item, list):
            result.extend(flatten(item))  # iç içe listeyi aç
        else:
            result.append(item)
    return result

input_data = [[1, 'a', ['cat'], 2], [[[3]], 'dog'], 4, 5]
output = flatten(input_data)
print(output)

#Proje 2. Tersine çeviren (reverse deeply) fonksiyon
def deep_reverse(lst):
    if isinstance(lst, list):
        return [deep_reverse(item) for item in reversed(lst)]
    return lst
input_data = [[1, 2], [3, 4], [5, 6, 7]]
output = deep_reverse(input_data)
print(output)
