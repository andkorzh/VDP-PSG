# Стандартные ячейки

Библиотека стандартных ячеек, применяемых в PSG.

Стандартные ячейки используют группу симметрии S2 (налево-направо + флип).

Комплементарка выведена наружу. Поэтому приходится все шланги в комплементе таскать.

Для всех ячеек - GND снизу.

## Ячейка 1 - not

|![image](https://user-images.githubusercontent.com/5828819/175828155-b9515f2e-2b66-4da4-86f1-a14564c949ac.png)|![image](https://user-images.githubusercontent.com/5828819/175999883-90b013b2-fc58-4027-9236-9763d79340f4.png)|
|---|---|

## Ячейка 2 - nand

|![image](https://user-images.githubusercontent.com/5828819/175828162-69dcf454-e27e-4bb9-aa23-9b45bb4da4f8.png)|![image](https://user-images.githubusercontent.com/5828819/175999920-ba876784-3b6e-4314-ab34-8da8cb6cd6b2.png)|
|---|---|

## Ячейка 3 - "99% not EDIT: ахах - нет!"

Было: ![image](https://user-images.githubusercontent.com/5828819/175828185-c3d8d309-6e06-4d31-9407-ce7882585c71.png)

На самом деле:

|![image](https://user-images.githubusercontent.com/5828819/176184195-b4206385-b0a0-4d57-b295-6e443fd7b300.png)|![image](https://user-images.githubusercontent.com/5828819/176184217-fb85430c-144a-4f3c-b6a2-906d04506b27.png)|
|---|---|

## Ячейка 4 - nand3

|![image](https://user-images.githubusercontent.com/5828819/175828193-f8cd0cd6-c3d2-421a-b0d5-5c432deee133.png)|![image](https://user-images.githubusercontent.com/5828819/176125415-f76623ef-382e-403c-807a-b7bc2bb4f5f4.png)|![image](https://user-images.githubusercontent.com/5828819/176121734-2aa7369c-96d0-4490-bcc4-e194179e0b00.png)|
|---|---|---|

## Ячейка 5 - dlatch

|![image](https://user-images.githubusercontent.com/5828819/175957768-2fb18bf3-0f28-4936-ae84-23d2bfefcf88.png)|![image](https://user-images.githubusercontent.com/5828819/176176744-37845b69-c7ca-467a-ad32-f080a0a57765.png)|![image](https://user-images.githubusercontent.com/5828819/176163672-2ecf4a9a-1797-4467-aa3d-549cbe394303.png)|
|---|---|---|

Комплементарный Enable вход.

## Ячейка 6 - comp (Комплементарный буфер)

Поскольку шнуровка для комплемента находится снаружи ячеек, для превращения одиночного "Enable" в два комплементарных сигнала используется этот комплементарный буфер. Плюс дополнительно он драйвит сигнал.

|![image](https://user-images.githubusercontent.com/5828819/175828255-fcc3b21d-1581-41ae-8568-4f52225abaf9.png)|![image](https://user-images.githubusercontent.com/5828819/176173811-0eb2c7bc-a7d0-4837-a69d-72a19f0c30f7.png)|![image](https://user-images.githubusercontent.com/5828819/176173863-f2a46577-6962-4659-8fe5-9afd277e9e84.png)|
|---|---|---|

## Ячейка 7 - or

|![image](https://user-images.githubusercontent.com/5828819/176176522-3a7d5767-a98e-496b-8528-05f6b4369565.png)|![image](https://user-images.githubusercontent.com/5828819/176018358-e445fd72-a8ca-4356-9f05-3e22aa7e1689.png)|
|---|---|

## Ячейка 8 - notif0

Управляемый инвертор с инверсным управлением.

|![image](https://user-images.githubusercontent.com/5828819/175957964-541661c6-e339-40c5-a8da-9e1b2a712aab.png)|![image](https://user-images.githubusercontent.com/5828819/176018237-bffd9aed-79f7-4be7-835f-edf27a565b64.png)|![image](https://user-images.githubusercontent.com/5828819/176018267-0b7643de-d56e-43f9-88f1-686f33d86382.png)|![image](https://user-images.githubusercontent.com/5828819/176018287-d56c1a19-cee0-4df7-8e19-1636e6f89323.png)|
|---|---|---|---|

## Ячейка 9 - cgi2a (Генератор переноса инвертирующий с одним инверсным входом)

|![image](https://user-images.githubusercontent.com/5828819/176394281-398de959-9b60-4f67-8a47-bf324a07b34a.png)|![image](https://user-images.githubusercontent.com/5828819/176394202-219d5798-68c0-426e-b91c-e4ea98f25c84.png)|![image](https://user-images.githubusercontent.com/5828819/176416783-97afc7bb-3122-49e3-963e-df0255f0fefb.png)|![image](https://user-images.githubusercontent.com/5828819/176416668-90045742-2111-4947-b2b2-57e993acc45a.png)|
|---|---|---|---|

Тут есть аналогичный, но с инверсным входом `b`: http://www.vlsitechnology.org/html/cells/vsclib013/cgi2b.html

Используется совместно с `aon2222` для создания счётчиков.

## Ячейка 10 - sr_bit

Разряд регистра сдвига. Дикая магия CMOS. Если убрать P-MOS часть, то ячейка принимает знакомый вид N-MOS разряда сдвигателя:

![image](https://user-images.githubusercontent.com/5828819/176033538-51ae5998-eaa3-4a6f-afd0-77f932a2fa79.png)

|![image](https://user-images.githubusercontent.com/5828819/175828434-def8dd3c-53b6-4d24-a516-ee5cc95f0329.png)|![image](https://user-images.githubusercontent.com/5828819/176033676-29be2ee5-71db-433f-bd14-1f58dde82434.png)|![image](https://user-images.githubusercontent.com/5828819/176033844-dfea478a-1031-477b-9ae1-519eba22c462.png)|
|---|---|---|

Использует комплементарные входы Load / Step.

Анализ работы:

![image](https://user-images.githubusercontent.com/5828819/176033609-a2666229-4ae3-45be-bd83-4faa5e3da96f.png)

Ещё поли:

![image](https://user-images.githubusercontent.com/5828819/176114115-4355ba98-e814-454e-9c3f-baf2cafca8f8.png)

После получения поли стало понятно что верхняя часть не соединяется с VDD (как видно там обрубок), в остальном угадали. Есть предположение, что в неокрепших умах инженеров YAMAHA всё ещё витали мечты о N-MOS защёлках на затворных емкостях. Сейчас использовать емкость на затворах в CMOS считается моветоном и используют обычные FF на двух инверторах или норах.

## Ячейка 11 - "ещё такая"

|![image](https://user-images.githubusercontent.com/5828819/175959809-c1862af9-696c-46fe-9019-12709208eeb8.png)|![image](https://user-images.githubusercontent.com/5828819/176185683-8d289499-4ab1-420b-b637-89162f41face.png)|
|---|---|

## Ячейка 12 - lfsr_bit

Используется для шумового канала. Ячейка представляет собой регистр сдвига с обратной связью. Выход замешивается на вход с тремя дополнительными замесами через операцию aoi.

|![image](https://user-images.githubusercontent.com/5828819/176185957-4371e9bc-bd7c-4fdf-ae42-a4ba08bfe53f.png)|![image](https://user-images.githubusercontent.com/5828819/176186226-52175d6f-51eb-4c15-8711-d784d491781b.png)|![image](https://user-images.githubusercontent.com/5828819/176441834-0ed8adde-0be3-4908-91df-5d793120713e.png)|![image](https://user-images.githubusercontent.com/5828819/176445322-e357dca8-04a7-45db-a2b7-b65063279168.png)|
|---|---|---|---|

Не стоит париться о глубоком смысле ячейки и зачем там внутри вкрячен aoi. Делай также и будет работать.

## Ячейка 13 - buf

|![image](https://user-images.githubusercontent.com/5828819/175828496-8fb2ec44-639f-4f8a-8e6e-b1a8025b9a3d.png)|![image](https://user-images.githubusercontent.com/5828819/176180281-5b7532e7-b7dd-46ef-bed6-73923f69fae2.png)|![image](https://user-images.githubusercontent.com/5828819/176180754-899c75fa-0af2-42f9-a165-b9d24792c974.png)|
|---|---|---|

## Ячейка 14+15

Было решено объединить их в одну, т.к. судя по всему это действительно одна мега-ячейка. Занимается скорее всего клоковым доменом (CLK Distribution).

|![image](https://user-images.githubusercontent.com/5828819/176186837-eefac41e-b4ba-426f-9a50-20cf0c258eb4.png)|![image](https://user-images.githubusercontent.com/5828819/176187126-68dec8b9-8d89-458e-b0a2-ad97e49e64cf.png)|![image](https://user-images.githubusercontent.com/5828819/176187306-69b78041-44e6-4965-b597-c64058f65cc4.png)|![image](https://user-images.githubusercontent.com/5828819/176187396-5416db50-3828-44ae-b9a8-6593ae666d41.png)|
|---|---|---|---|

## Ячейка 16 - aoi21

|![image](https://user-images.githubusercontent.com/5828819/176190468-ce3e51af-3965-48fd-8d4b-206356d4bfb3.png)|![image](https://user-images.githubusercontent.com/5828819/176204015-86bfb3b8-1ac9-422a-a3d6-2425245dcb38.png)|![image](https://user-images.githubusercontent.com/5828819/176261618-758d3c39-f3da-45cc-a9c7-e5d9bdc8461c.png)|![image](https://user-images.githubusercontent.com/5828819/176261661-e501a05f-9ca6-49e5-b3e1-098a2298788c.png)|
|---|---|---|---|

http://www.vlsitechnology.org/html/cells/vsclib013/aoi21.html

## Ячейка 17 - and3

|![image](https://user-images.githubusercontent.com/5828819/176190699-3541d3df-5827-4a84-bb0a-913818436337.png)|![image](https://user-images.githubusercontent.com/5828819/176204233-07d70da0-d0ae-457c-802b-b3fdbe04417b.png)|![image](https://user-images.githubusercontent.com/5828819/176273560-1e9a28fb-d50f-49e5-96a2-029db8205bba.png)|![image](https://user-images.githubusercontent.com/5828819/176273591-cda98f3c-f6e0-4f42-80df-7a1df5b5fc77.png)|
|---|---|---|---|

## Ячейка 18 - "большая 3"

|![image](https://user-images.githubusercontent.com/5828819/175959078-5cf9f231-baaa-4a33-add7-f35cdb7e9b32.png)|![image](https://user-images.githubusercontent.com/5828819/176202271-89a9a869-eba8-4442-9162-ad07cdecd52f.png)|
|---|---|

## Ячейка 19 - "ктулху"

|![image](https://user-images.githubusercontent.com/5828819/175959384-6d79e735-510f-4cd9-a2bb-2bce819033a5.png)|![image](https://user-images.githubusercontent.com/5828819/176203046-43f896aa-574d-455b-9ce8-fea1b477f5df.png)|
|---|---|

В единственном экземпляре в правом нижнем углу.

## Ячейка 20 - "мощный писюн"

|![image](https://user-images.githubusercontent.com/5828819/175965602-246a1d11-7b25-4778-815f-2e8ef21c58b4.png)|![image](https://user-images.githubusercontent.com/5828819/176202632-86301523-d5da-4f63-9549-7179b89989be.png)|
|---|---|

В правом верхнем углу. Также ряд `H`.

## Ячейка 21 - "дошик"

|![image](https://user-images.githubusercontent.com/5828819/176191076-13161844-1df5-4ac7-90df-2fc926a6915c.png)|![image](https://user-images.githubusercontent.com/5828819/176198129-7f378890-1469-4076-a226-027ca1623969.png)|
|---|---|

Встречается в ряду `G`.

## Ячейка 22 - xor

|![image](https://user-images.githubusercontent.com/5828819/176287353-e5aa4c25-c5ad-488b-b5ed-8a5a0bb7fe38.png)|![image](https://user-images.githubusercontent.com/5828819/176198629-096293c4-8224-41a3-9133-3c87889a9ea4.png)|![Cell22_topo](/imgstore/Cell22_topo.png)|![image](https://user-images.githubusercontent.com/5828819/176373559-127b9114-b944-4a54-af8c-263289dfe1b4.png)|![image](https://user-images.githubusercontent.com/5828819/176373596-dae9d4c7-592c-4829-99ff-055d552ea4be.png)|
|---|---|---|---|---|

В единственном экземпляре, по середине ряда `G`.

## Ячейка 23 - "что-то там по середине закрашено"

|![image](https://user-images.githubusercontent.com/5828819/176144811-5e6adfbd-b1f2-4581-a6d5-d1d0145d84e4.png)|![image](https://user-images.githubusercontent.com/5828819/176199363-e7ef2c94-cf95-41e6-a921-289226d8481f.png)|
|---|---|

В единственном экземпляре, по середине ряда `H`.

## Ячейка 24 - rs

|![image](https://user-images.githubusercontent.com/5828819/176145611-63770541-ccd9-43e7-be5c-61badbb8c6af.png) ![image](https://user-images.githubusercontent.com/5828819/176260167-7acbff60-b5c9-4618-900e-3ab78da10f82.png)|![image](https://user-images.githubusercontent.com/5828819/176200419-f0a31bce-8d44-49dd-b2ca-4f85cd8f84c9.png) ![image](https://user-images.githubusercontent.com/5828819/176273044-a6c54232-eb47-4ad9-86bf-8f30cc6177a0.png)|
|---|---|

![image](https://user-images.githubusercontent.com/5828819/176285077-d3d89ffc-4052-4367-82ab-aaafcdb1dfd6.png)

Порт `a` - Set, порт `b` - Reset.

В двух экземплярах, ряд `H`.

Анализ:

![image](https://user-images.githubusercontent.com/5828819/176284957-6244b979-da7a-48d0-bd4b-9317c8e096a7.png)

Видно что разработчики оставили выход `~Q`, но он не задействован.

## Ячейка 25 - aon2222 (4x 2-AND into 2-OR gate)

|![image](https://user-images.githubusercontent.com/5828819/176393083-80837fdc-e63d-4d79-a2a8-7cea6be5ed70.png)|![image](https://user-images.githubusercontent.com/5828819/176393449-6233fcdf-39d9-4e83-b4d7-0fa9069acc88.png)|![image](https://user-images.githubusercontent.com/5828819/176415164-af7859e6-c98a-46a8-bbad-f7802ecc6627.png)|![image](https://user-images.githubusercontent.com/5828819/176415203-61de00b8-e2e5-4220-ad54-23318e6cae00.png)|
|---|---|---|---|

Используется совместно с `cgi2a` для создания счётчиков.

Выход ора подаётся на инвертирующий вход `a` генератора переноса.
