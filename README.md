Operator 

Overloading Operator overloading bruges også i java, her kan man ikke skrive sine egne. Der findes to typer af Operator Overloading. De Unary og de Binary. 

- Unary Operators: De tager et argument og et symbol. 
+a kalder a.unaryPlus() 
-a kalder til a.unaryMinus() 
!a kalder a.not() 

+a giver som udgangspunkt ikke rigtig mening, da man antager en værdi er positiv til at begynde med. Men hvis du har en værdi som eksempelvis kan være +2 eller -2, så kan man sætte assigne den til a og bruge +a, for at sikre sig at a=2. - Binary Operators: de tager to argumenter og et symbol

a + b kalder a.plus(b) 
a - b kalder a.minus(b) 
a * b kalder a.times(b) 
a / b kalder a.div(b) 
a % b kalder a.mod(b) a..b kalder a.rangeTo(b) 

Det er operationer som vi har brugt mange gange i java og funktionen af dem giver lidt sig selv.

Kotlin har de samme array operations som i java. Så hvis man eksempelvis vil assigne værdi Eksempel: fun main(args: Array<String>) {

val myList: IntArray = intArrayOf(10, 20, 30, 40, 50) myList[2] = 4 // myList.set(2,4) val x = myList[2] print(x) } myList[2] = 4 Kunne i princippet også skrives som : myList.set(2,4), hvis man ikke brugte operator overloading. I Kotlin kan man skrive custom Operation overloaders Anton Ioleiva kommer med følgende eksempel:

data class ForecastList(val city: String, val country: String, val dailyForecast: List<Forecast>) { public fun get(position: Int): Forecast = dailyForecast[position] public fun size(): Int = dailyForecast.size()

} Her overskriver han funktionen til hans liste, så han i stedet for at skulle skrive

val forecast = weekForecast.dailyForecast[position]

i stdet kan skrive :

val forecast = weekForecast[position] Er det så smart ? Han skriver selv at man skal være meget påpasselig med at lave de her Operation Overloads og det bør kun gøres hvis det er meget tydeligt hvad de rent faktisk gør.

Det giver god mening når man har to integers at man kan bruge a+b. Men hvis lige pludeslig laver nye overload metode som eksempelvis kan: 
-lægge to kreditkontoer sammen 
- lægge værdien af to huse sammen 
- lægge værdien af to aktier sammen 

Så afgøres det af typen som den bliver kaldt med hvilken af de forskellige overload metoder som bliver kaldt. Dette kan hurtigt blive forvirrende, når man skal læse andres kode. Det kan også gøre det svært at debugge, da man skal tage højde for flere forskellige overload metoder som ikke nødvendigvis fungere ens.

-Thomas
