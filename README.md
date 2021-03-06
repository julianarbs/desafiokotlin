# desafiokotlin

Introdução
1. fun main(args: Array<String>) 
{
    val input = Scanner(System.`in`)
    val a = input.nextInt()
    val b = input.nextInt()

    println("SOMA = " + (a + b)) 
}

2. fun main(args: Array<String>) 
{
    for (i in 1.rangeTo(readLine()!!.toInt()).step(2)) println(i)
}

3. fun main(args: Array<String>) 
{
    var r = 0
    
    for (i in 1..readLine()!!.toInt()) {
        println("${i} ${ i * i } ${ i * i * i }") 
        r += 0
    }
}

Solucionando
1. fun main(args: Array<String>) 
{
  fun Double.format(digits: Int) = "%.${digits}f".format(this).replace(',', '.')

  val valor = readLine()!!.toDouble()
  var imposto = 0.0
  var diferenca: Double

  if (valor > 4500) {
    imposto = 1000 * 0.08 + 1500 * 0.18
    diferenca = valor - 4500
    imposto += diferenca * 0.28
  } else if (valor > 3000) {
    imposto = 1000 * 0.08
    diferenca = valor - 3000
    imposto += diferenca * 0.18
  } else if (valor > 2000) {
    diferenca = valor - 2000
    imposto = diferenca * 0.08
  }
  
  if (imposto == 0.0) println("Isento") else println("R$ ${imposto.format(2)}")
}

2.import java.math.BigDecimal
import java.math.RoundingMode
import java.util.*
import kotlin.math.pow

fun main(args: Array<String>) 
{
    val raio = readLine()?.toDouble()
    val pi = 3.14159
  
    raio?.let {
        val area = pi*raio.pow(2)
        val resultado = BigDecimal(area).setScale(4, RoundingMode.HALF_EVEN)
        
        println("A=$resultado")
    }
}

3. import kotlin.math.sqrt

fun main() 
{
    val n = readLine()!!.toInt()
    
    for (i in 0 until n) {
        var x = readLine()!!.toDouble()
        val prime = isPrime(x)
        
        print(prime)
    }
}

fun print(prime: Boolean) 
{
    if (prime) {
        print("Prime\n")
    } else print("Not Prime\n")
}

fun isPrime(num: Double): Boolean 
{
    if (num < 2) return false
    if (num % 2 == 0.0) return num == 2.0
    
    val root = sqrt(num).toInt()
    var i = 3
    
    while (i <= root) {
        if (num % i == 0.0) return false
        i += 2
    }
    
    return true
}

4.import java.io.EOFException
import java.lang.Exception

fun main(args: Array<String>) 
{
    while (true) {
        try {
            val l = readLine()!!.toInt()
            val v = readLine()!!.split(" ").run { map { it.toInt() } }
            val sorted = v.toTypedArray()
            
            sorted.sort()
            
            when (sorted.last()) {
                in 0 .. 9 -> {
                    println(1)
                }
                
                in 10 .. 19 -> {
                    println(2)
                }
                
                else -> {
                    println(3)
                }
            }
        
        } catch (f: Exception) {
            break
        } catch (n:Exception) {
            break
        } catch (e:Exception) {
            break
        }
    }
}

5.fun main(args: Array<String>) 
{
    val lista = mutableListOf<Int>()
    
    for (i in 1..readLine()!!.toInt()) {
        val input = readLine()!!.split(" ").map { it.toInt() }
        
        input.forEach { number ->
            lista.add(number)
        }

        println(mdc(lista[0], lista[1]))
        
        lista.clear()
    }
}

fun mdc(n1: Int, n2: Int): Int 
{
    return if (n2 == 0) {
        n1
    } else {
        mdc(n2, (n1 % n2))
    }
}


Praticando 
1. fun main(args: Array<String>) {  
    val N = readLine()!!.toInt()
    
    for (i in 1..N) {
        val range1 = 'A'..'Z'
        val range2 = 'a'..'z'
        
        val line = readLine()!!
        
        for (letter in range1) {
            if (line.contains(letter)) {
                val list = line.split(letter).map { it.toInt() }
                
                val N1 = list[0]
                val N2 = list[1]
                
                if (N1 == N2) {
                    println(N2 * N1)
                } else {
                    println(N2 - N1)
                }
            }
        }
        
        for (letter in range2) {
            if (line.contains(letter)) {
                val list = line.split(letter).map { it.toInt() }
                
                val N1 = list[0]
                val N2 = list[1]

                if (N1 == N2) {
                    println(N2 * N1)
                } else {
                    println(N2 + N1)
                }
            }
        }
    }
}

2. fun main(args: Array<String>) {
    var s: String
    var n: Int
    val r = "0x"
    
    while (true) {
        val s = readLine()!!
        
        try {
            val value = s.toInt()
            
            if (value == -1) {
                break
            }
        } catch (e: Exception) {}
        
        if (s.contains(r)) {
            hexaToDecimal(s)
        } else {
            decimalToHexa(s)
        }
    }
}

fun decimalToHexa(s: String) {
    val n = s.toInt()
    
    print("0x${Integer.toHexString(n).toUpperCase()}\n")
}

fun hexaToDecimal(s: String) {
    val hex = s.subSequence(2, s.length).toString()
    val n = Integer.parseInt(hex, 16)
    
    print("$n\n")
}

3.import java.util.Scanner

fun main() {
    for (i in 1..readLine()!!.toInt()) {
        val canos = readLine()!!.split(" ").map { 
            it.toInt() 
        }
        
        val r1 = canos[0]
        val r2 = canos[1]
        
        println(r1 + r2)
    }
}
