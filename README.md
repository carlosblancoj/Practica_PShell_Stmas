# Análisis y documentación de scripts
Consiste en analizar y documentar los siguientes scripts de Powershell. Para ello, es necesario el uso del cmdlet **Set-ExecutionPolicy** con el parámetro **Unrestricted** que permite ejecutar cualquier script, sea cual sea su fuente.

![alt_text](https://github.com/carlosblancoj/Practica_PShell_Stmas/blob/main/Capturas/4.PNG)
## · Script 1
~~~
$number = 1
Write-Host "The number is: " $number
~~~
Primero se declara una variable entera y luego, mediante el cmdlet **Write-Host** que será una constante durante todo el ejercicio, la función comunica a un determinado host un output personalizado junto a la variable declarada.

![alt_text](https://github.com/carlosblancoj/Practica_PShell_Stmas/blob/main/Capturas/1.PNG)
## · Script 2
~~~
[int]$repeat = 5
for ($counter = 0; $counter -lt $repeat; $counter++) {
    Write-Host "hello"
} 
~~~
Construcción de un bucle **For**, es decir, cada vez que se completa el ciclo, el código entre paréntesis se ejecutará mientras $counter sea menor que $repeat. De este modo, cada vez que se completa el ciclo las variables se incrementan en uno mediante el símbolo ++.
~~~
[int]$repeat = 5
[int]$counter = 0
while ($counter -lt $repeat) {
    Write-Host "hello"
    $counter++
}
~~~
Construcción de un bucle **While**, es decir,  el ciclo continuará hasta que $counter sea menor que (-lt) el valor 5 contenido en la variable $repeat.
~~~
[int]$repeat = 5
[int]$counter = 0
do {
    Write-Host "hello"
    $counter++
}
while ($counter -lt $repeat)
~~~
Construcción de un bucle de la variante **Do While**, en el cual el código se ejecuta antes de verificar la condición para ver si se repite.
~~~
[string]$stringOfCharacters = "PowerShell for Beginners"
foreach ($character in $stringOfCharacters.ToCharArray()) {
    Write-Host $character
} 

[string]$stringOfCharacters = "PowerShell for Beginners"
$stringOfCharacters.ToCharArray() | ForEach-Object { Write-Host "$_" }
~~~ 
Construcción de un bucle de la variante **For Each**, en el cual cada vez que se completa el bucle, la variable $character se convierte en el siguiente carácter de la lista hasta que no queden caracteres.

![alt_text](https://github.com/carlosblancoj/Practica_PShell_Stmas/blob/main/Capturas/2.PNG)
![alt_text](https://github.com/carlosblancoj/Practica_PShell_Stmas/blob/main/Capturas/2.1.PNG)
## · Script 3
~~~
if (4 -eq 4) {
    Write-Host "4 is equal to 4"
}
if ("hello" -eq "hello") {
    Write-Host "Both strings are equal to each other"
}
~~~
Si los valores en la declaración **If** son iguales, entonces el resultado de la declaración da como resultado una condición verdadera. De ser así, entonces se ejecuta el código dentro de los corchetes.
~~~
[int]$x = 10
[int]$y = 10
if ($x -eq $y) {
    Write-Host "the x and y variables are equal to each other"
}
else {
    Write-Host "The x and y variables are NOT equal to each other"
}
~~~
Si cambia el valor de una de las variables, no se igualarán entre sí, por lo que se ejecutará la cláusula **Else**.
~~~
[string]$playerInput = ""
$playerInput = Read-Host -Prompt "You walk into a room with two doorways. One to the left and one to the right. Type 'left' or 'Right' to walk through one of the doors."

if ($playerInput -eq "left") {
    Write-Host "Player typed left"
}
elseif ($playerInput -eq "right") {
    Write-Host "Player typed right"
}
else {
    Write-Host "Player typed something we didn't understand"
}
~~~
Lectura de entrada desde la consola mediante el cmdlet **Read-Host** y posterior uso de declaraciones **If, Elseif, Else** para mostrar un resultado u otro según la toma de decisiones del usuario.
~~~
# Operator numbers
if (1 -lt 2) {
    #1 is less than 1
}
# Operator strings
if ("HELLO" -match "H") {
    #H exists in the 
    Write-Host "HELLO"
}
# Operator lists 	
$list = @(1, 2, 3, 4, 5)
if ($list -notcontains 8) {
    #$list does not contain 8
}
~~~
Ejemplos de operadores con distintos tipos de variables combinados con declaraciones **If**.
~~~
[string]$favouriteColour = "Blue"
switch ($favouriteColour) {
    "Red" {
        "Your favourite colour is Red"
        "I like red too."
    }
    "Blue" {
        "Your favourite colour is Blue"
        "I like Blue too."
    } 
    default { "I dont recognise that colour" }
}
~~~
Ejemplo de declaración **Switch**, empleado para mostrar dentro de cada cláusula que puede ejecutar varias líneas de código, no solo una.
La cláusula final **Default** es predeterminada y se ejecutará si ninguno de los valores coincide.

![alt_text](https://github.com/carlosblancoj/Practica_PShell_Stmas/blob/main/Capturas/3.PNG)
![alt_text](https://github.com/carlosblancoj/Practica_PShell_Stmas/blob/main/Capturas/3.2.PNG)
