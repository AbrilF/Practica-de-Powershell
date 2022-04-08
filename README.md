# Practica-de-Powershell
### Script de powershell 1
```

$number = 1 #Crea la variable llamada number y asigna el valor 1 a esta.

Write-Host "The number is: " $number #Imprime por pantalla la variable anterior.

$number = 2 #Rescribe la variable anterior con un 2.

Write-Host "The number is: " $number #Imprime por pantalla la variable anterior.

$number = 3 #Rescribe la variable anterior con un 3.

Write-Host "The number is: " $number #Imprime por pantalla la variable anterior.

$number = 4 #Rescribe la variable anterior con un 4.

Write-Host "The number is: " $number #Imprime por pantalla la variable anterior.

```
---
### Script de powershell 2
```

# Este bucle cada vez que se complete se ejecutará si $counter es menor que $repeat.
# Ademas el bucle cada vez que se complete, los símbolos ++ le diran a la variable que aumente uno cada vez.
[int]$repeat = 5

for ($counter = 0; $counter -lt $repeat; $counter++) {
    Write-Host "hello"
} 

#El bucle de While, no parara hasta que $contador sea menor que ''-lt'' el valor 5 contenido en la variable $repeat .
[int]$repeat = 5
[int]$counter = 0

while ($counter -lt $repeat) {
    Write-Host "hello"
    $counter++
}

# El bucle de Do While es una variante del bucle while, excepto que el código se ejecuta antes de verificar la condición para ver si se repite.
[int]$repeat = 5
[int]$counter = 0
do {
    Write-Host "hello"
    $counter++
}
while ($counter -lt $repeat) 

# ForEach bucles,cada vez que se completa, la variable $character se convierte en el siguiente caracter de la lista hasta que no queden mas caracteres.
[string]$stringOfCharacters = "PowerShell for Beginners"

foreach ($character in $stringOfCharacters.ToCharArray()) {
    Write-Host $character
} 

# ForEach-Object bucles,que permite realizar bucles de forma simple y directa. 
[string]$stringOfCharacters = "PowerShell for Beginners"
$stringOfCharacters.ToCharArray() | ForEach-Object { Write-Host "$_" }

```
---
### Script de powershell 3

```

# Si los valores en if son iguales, entonces el resultado de esta da como resultado verdadero.
# Ademas si da como resultado verdadero, entonces se ejecuta el codigo dentro de los corchetes {}.
if (4 -eq 4) {
    Write-Host "4 is equal to 4"
}

if ("hello" -eq "hello") {
    Write-Host "Both strings are equal to each other"
} 

# Si cambias el valor de una de las variables, no se igualaran entre si, por lo que se ejecutara el else.
[int]$x = 10
[int]$y = 10

if ($x -eq $y) {
    Write-Host "the x and y variables are equal to each other"
}
else {
    Write-Host "The x and y variables are NOT equal to each other"
}

# El resultado es verdadero y se ejecuta el código dentro de la instrucción if, ya que la respuesta es verdadera.
$yourName = "Ian"

if ($yourName -eq "Ian") {
    Write-Host "Hay my name is Ian too!"
}
else {
    Write-Host "Hi $yourName, nice to meet you!"
}

# An example of reading input from the console and using an if, elseif, else statements.
# Using just this code you can expand it to write your own text based adventure game in PowerShell!
#Variables
[string]$playerInput = ""

# Consigue el input de player.
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


# Operadores de comparacion.

# -eq	Equals.	
if (5 -eq 5) {
    #5 is equal to 5
}
   
# -ne Not equals.
if (3 -ne 4) {
    #3 is not equal to 4
}
   
# -gt Greater than.
if (4 -gt 2) {
    #4 is greater than 2
}
   
# -ge Greater than or equal.
if (2 -ge 1) {
    #2 is greater than or equal to 1
}
   
# -lt Less than.
if (1 -lt 2) {
    #1 is less than 1
}

# -le Less than or equal.
if (1 -le 2) {
    #1 is less than or equal to 2
} 

# -like da como resultado verdadero cuando una cadena coincide con la de un carácter *.
# La cadena "hello*" dice si esta cadena coincide con la otra comenzando con la palabra hola seguida de cualquier otra palabra.
# Si usamos "*hello*" significa que el resultado es verdadero si hellow aparece en la otra cadena porque estamos usando * al principio y al final.	
if ("hello how are you?" -like "hello*") {
    #use a wildcard character * to match strings
}

# -notlike da como resultado verdadero cuando dos cadenas no coinciden.	
if ("HELLO" -notlike "BYE") {
    #HELLO is not like BYE
} 

# -match da como resultado verdadero cuando una cadena coincide con un patrón de expresión regular. 
if ("HELLO" -match "H") {
    #H exists in the 
    string "HELLO"
}
   
# -notmatch	da como resultado verdadero cuando una cadena no coincide con un patron de expresion regular.	
if ("HELLO" -notmatch "A") {
    #A does not match in the 
    string "HELLO"
}

# -contains	da como resultado verdadero cuando se encuentra un valor dentro de otra coleccion.
$list = @(1, 2, 3, 4, 5)
if ($list -contains 3) {
    #the list does contain a 3
}

# -notcontains da como resultado verdadero cuando no se encuentra un valor dentro de una coleccion.	
$list = @(1, 2, 3, 4, 5)
if ($list -notcontains 8) {
    #$list does not contain 8
}

# -in	da como resultado verdadero cuando se encuentra un valor en una coleccion.	
$list = @(1, 2, 3, 4, 5)
if (3 -in $list) {
    #the list does contain a 3
} 

# -notin	da como resultado verdadero cuando un valor no se encuentra en una coleccion.	
$list = @(1, 2, 3, 4, 5)
if (6 -notin $list) {
    #6 is not in the list
}

# -is	da como resultado verdadero cuando una variable o valor coincide con el tipo especificado.	
$var = "This is a string"
if ($var -is [string]) {
    #The variable is a string
}

# -isnot	da como resultado verdadero cuando una variable o valor no es igual al tipo especificado.	
$var = "This is a string"
if ($var -isnot [bool]) {
    #The variable is a string and not a Boolean value so results in true.
} 
   

# Switch Statements

# En este ejemplo, configuramos un numero de variables y lo pasamos al interruptor.
# En cada linea colocamos el valor con el que comparar.
# En este caso, los numeros 1 y 2 y despues de cada valor usamos corchetes {} para definir el código que se ejecutara cuando ese valor coincida.
[int]$number = 2
switch ($number) {
    1 { "The number is one" }
    2 { "The number is two" }
    default { "I dont know what the number is" }
}

# Esto muestra dentro de cada parte que puede ejecutar varias lineas de codigo, no solo una.
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


```
