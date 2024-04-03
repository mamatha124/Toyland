# Toyland in python
num = int(input().strip())
houses = []
for i in range(num):
    houseNum, pos = map(int, input().strip().split())
    houses.append((houseNum, pos))
houses = sorted(houses, key=lambda x: x[1])
max_distance = 0
house1, house2 = 0, 0
for i in range(1, num):
    distance = houses[i][1] - houses[i-1][1]
    if distance > max_distance:
        max_distance = distance
        house1, house2 = houses[i-1][0], houses[i][0]
if house1 > house2:
    house1, house2 = house2, house1
print(house1, house2)
