# Заметки по топологии

Ячейки расставляли и соединяли проводами вручную. Фиттер так не расставит красиво и роутер не соединит.

![image](https://user-images.githubusercontent.com/5828819/175983109-d13f8b43-3bb9-4e85-842e-b8bf61fdd92b.png)

Это человек делал.

![image](https://user-images.githubusercontent.com/5828819/175983175-84c133a4-d846-4451-81fe-b535a47a4efd.png)

И ячейки уложены модульно (что собсно у @nukeykt на картинках видно - каунтер отдельно, регистры отдельно и проч.)

VDP - CMOS с одним слоем металла.

![image](https://user-images.githubusercontent.com/5828819/175983002-4df8cd5c-90a1-49fe-9fc4-dbe16c287375.png)

https://www.icreversing.com/chips/315-5313a

Ещё одной необычной особенностью является использование n-карманов, вместо привычных p:

![image](https://user-images.githubusercontent.com/5828819/176116906-edc63b0e-4829-4dec-9c4e-634e062aece4.png)

При реверсе не стоит на это обращать внимание. Там где земля - с той стороны N-трансы, там где VDD - с той стороны P-трансы, обычные правила для CMOS.

## Карта ячеек

![PSG_netlist](/imgstore/PSG_netlist.png)

## Модули

Карта распределения ячеек по модулям, by @nukeykt.

![image](https://user-images.githubusercontent.com/5828819/176502964-95bc5798-02ce-4933-ac8c-da426f77f7a4.png)

## Группа самосовмещений ячеек

В некоторых местах встречается такое (земля снизу):

![image](https://user-images.githubusercontent.com/5828819/176856526-86d02e64-7d99-4f38-9a79-cd850feba478.png)

Казалось бы это две ячейки `or`, но нет.

Группа самосовмещений (ячейка `or`):

|ident (земля снизу)|rot (земля сверху)|flip_h (земля снизу)|rot+flip_h (земля сверху)|
|---|---|---|---|
|![image](https://user-images.githubusercontent.com/5828819/176852861-7d7a0f57-d302-4f71-bd27-1cea605fb091.png)|![image](https://user-images.githubusercontent.com/5828819/176852945-8082ee45-692c-42dc-92d7-c90748a3aae1.png)|![image](https://user-images.githubusercontent.com/5828819/176853301-54b26e7c-8166-430b-9e86-bc5045b9614b.png)|![image](https://user-images.githubusercontent.com/5828819/176857460-1020e86c-4dcd-4f58-824e-76e226a66e25.png)|

Т.е. понятно что ячейка не может быть повернута вверх (т.к. они уложены рядами) и не может быть флипнута вертикально (снизу-вверх), т.к. в этом случае мы получаем картину, что была показана вначале.

Ячейка `or` флипнутая по вертикали меняет N и P транзисторы, оставляя землю, поэтому становится ячейкой `and`.

Поэтому у ячейки `and` будет такая группа самосовмещений:

|ident (земля снизу)|rot (земля сверху)|flip_h (земля снизу)|rot+flip_h (земля сверху)|
|---|---|---|---|
|![image](https://user-images.githubusercontent.com/5828819/176853681-b5759600-34d0-4bc9-be78-0f6d9d245eaa.png)|![image](https://user-images.githubusercontent.com/5828819/176853715-74e3c938-3f99-410f-bbf8-6dd91cbcbb9e.png)|![image](https://user-images.githubusercontent.com/5828819/176853767-57d5a1f7-5c1b-4c51-b9e7-fd7c9e5a4074.png)|![image](https://user-images.githubusercontent.com/5828819/176857641-2b40c1dc-3858-439d-addf-e99a83b466ba.png)|

Не все ячейки позволяют такие фокусы, а только комплементарно симметричные, типа nor / nand, or / and.

Группа самосовмещений ячеек является простейшей группой диэдра D2 (`Vierergruppe`).

![image](https://user-images.githubusercontent.com/5828819/176861596-9f27ad7b-82f0-4c9a-888c-5250f60a61ae.png)

## Сложное место 1

![image](https://user-images.githubusercontent.com/5828819/184116473-0a559c73-04f9-477a-b29c-6ea19f5d8601.png)

![image](https://user-images.githubusercontent.com/5828819/184116399-5b6009ca-f460-45cf-afac-3bc48c5ff6c8.png)

![image](https://user-images.githubusercontent.com/5828819/184116636-3bea6b60-9854-4c65-9748-caab3aafb119.png)

![image](https://user-images.githubusercontent.com/5828819/184116668-55414386-a55f-4c5c-984e-625ac3949229.png)

![image](https://user-images.githubusercontent.com/5828819/184116530-c68b4d8f-894b-4def-ba59-f04c6eb233ed.png)

## Контстантные выходы

В некоторых местах в схему уходят константные значения (Vdd/Vss).

Выглядят они так:

Константный `0` (GND сверху):

|![image](https://user-images.githubusercontent.com/5828819/184126459-67473727-e2c8-416a-9de4-8aa743b211da.png)|![image](https://user-images.githubusercontent.com/5828819/184126531-13cc3699-9d93-47cc-8a01-d679ee6c3d27.png)|![image](https://user-images.githubusercontent.com/5828819/184126772-f7cb6d43-75b7-499c-bfb1-50340b359599.png)|
|---|---|---|

Константный `1` (GND сверху):

|![image](https://user-images.githubusercontent.com/5828819/184126643-c0545d85-1fd4-460f-82b2-5d3ecc3b1ef3.png)|![image](https://user-images.githubusercontent.com/5828819/184126919-0ca2fd29-95e4-4581-96c5-9a3ab72f9990.png)|
|---|---|
