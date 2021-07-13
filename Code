import java.lang.Exception

fun main() {
    var stringA = "|       |"
    var stringB = "|       |"
    var stringC = "|       |"
    var coordinatsA = 0
    var coordinatsB = 0
    var player = "X"
    var drawCounter = 0



    println("---------")
    println("|       |")
    println("|       |")
    println("|       |")
    println("---------")

   loop@while (true) {
        println("Enter the coordinates:")
        var (a, b) = readLine()!!.split(" ")
        try {
            coordinatsA = a.toInt()
            coordinatsB = b.toInt()
        } catch (NumberFormatException: Exception) {
            println("You should enter numbers!")
            continue
        }
        if (coordinatsA !in 1..3 || coordinatsB !in 1..3) {
            println("Coordinates should be from 1 to 3!")
            continue
        }


        when (coordinatsB) {
            1 -> coordinatsB = 3
            2 -> coordinatsB = 5
            3 -> coordinatsB = 7
        }
        when (coordinatsA) {
            1 -> {
                if (stringA[coordinatsB - 1].toString() == "X" || stringA[coordinatsB - 1].toString() == "O") {
                    println("This cell is occupied! Choose another one!")
                    continue
                }
            }
            2 -> {
                if (stringB[coordinatsB - 1].toString() == "X" || stringB[coordinatsB - 1].toString() == "O") {
                    println("This cell is occupied! Choose another one!")
                    continue
                }
            }
            3 -> {
                if (stringC[coordinatsB - 1].toString() == "X" || stringC[coordinatsB - 1].toString() == "O") {
                    println("This cell is occupied! Choose another one!")
                    continue
                }
            }
        }


        when (coordinatsA) {
            1 -> {
                stringA = stringA.substring(0, coordinatsB - 1) + player + stringA.substring(coordinatsB, stringA.length)
            }
            2 -> {
                stringB = stringB.substring(0, coordinatsB - 1) + player + stringB.substring(coordinatsB, stringB.length)
            }
            3 -> {
                stringC = stringC.substring(0, coordinatsB - 1) + player + stringC.substring(coordinatsB, stringC.length)
            }
        }

        println("---------")
        println(stringA)
        println(stringB)
        println(stringC)
        println("---------")


        drawCounter++
        if (drawCounter == 9) {
            println("Draw")
        }

        // Win Conditioin

        var array = arrayOf(stringA, stringB, stringC)

        for (str in array) {
            if (str[2].toString() == player && str[4].toString() == player && str[6].toString() == player) {
                print("$player wins")
                break@loop
            }
        }

        for (i in 2..6 step 2) {
            if (stringA[i].toString() == player && stringB[i].toString() == player && stringC[i].toString() == player){
                println("$player wins")
                break@loop
            }
        }

       if (stringA[2].toString() == player && stringB[4].toString() == player && stringC[6].toString() == player || stringA[6].toString() == player && stringB[4].toString() == player && stringC[2].toString() == player) {
           println("$player wins")
           break@loop
       }


        if (player == "X") {
            player = "O"
        } else {
            player = "X"
        }

    }

}
