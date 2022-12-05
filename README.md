using System.Globalization;
using System.Reflection;
using System.Security.Cryptography.X509Certificates;

namespace Saquenme_de_aquii
{
    internal class Program
    {
        private static void Main(string[] args)
        {
            //En esta parte del codigo ingresa los vectores el usuario en este casio Usted //
            int Selecciona;
            Console.WriteLine("Por favor ingresa los vectores Beni(: " +
                "\nDespués de ingresar un número, por favor da doble click");

            int numeros = 0;
            int[] Mini = new int[10];
            int i = 0 ;

            while (i < Mini.Length)
            {
                Console.WriteLine("Solo números entre 1 y 80");
                numeros = int.Parse(Console.ReadLine());
                if (numeros >= 1 && numeros <= 80)
                {
                    Mini[i] = numeros;
                    i++;
                }
                else
                {
                    Console.WriteLine("Por favor Beni, solo numero del 1 al 80 para que no sea largo");
                }

            }
            Console.Clear();
            Console.WriteLine("Tus números ingresados son estos: ");
            foreach (int temp in Mini)
            {
                Console.Write(temp+" ");
            }
            Console.ReadKey();
            //Despues ingresado los vectores se despliega unmenu con opciones de roblemas que puede resolver //
            Console.WriteLine("Ingresa que problema deseas hacer:\n" +
                "\nProblema 1.- Invrtir tus Números" +
                "\nProblema 2.- Averigue si l alista esta ordenada de menor a mayor" +
                "\nProblema 3.- Averiue si esta ordenado de manera creciente " +
                "\nProblema 4.- Averigue si hay numero repetidos" +
                "\nProblema 5.- Ordenar de menor a mayor " +
                "\nProblema 6.- Averiguar si un numero esta en la lista" +
                "\nProblema 7.- Calcula el promedio de los numeros ingresados");
            int op = 0;
            op = Convert.ToInt16(Console.ReadLine());
            //Dependiendo la respuesta te guia a una de la siguientes opciones//
            switch (op)
            {
                case 1:
                    Console.Clear();
                    Console.Write("Invertir Números");
                    int cam = Mini.Length - 1;
                    string num1 = " ";
                    while (cam > 0)
                    {
                        num1 = num1 + Mini[cam];
                        cam = cam - 1;
                    }
                    Console.WriteLine("\nTu número al reves es este: " + num1 n+ " ");
                    Console.ReadKey();
                    break;
                case 2:
                    Console.Clear();
                    Console.Write("Esta de menor a mayor\n ");

                    i = 0;
                    for (int j = 1; j < 10; j++)
                    {
                        if (Mini[j - 1] < Mini[j])
                        {
                            i++;
                        }
                    }

                    if (i == 9)
                    {
                        Console.WriteLine("SI esta");
                    }
                    else
                    {
                        Console.WriteLine("NO esta");
                    }

                    break;
                case 3:
                    Console.Clear();
                    Console.Write("Averiguar si esta de manera creciente\n ");
             
                    int A = 1;
                    i = 0;
                    for (int j=1;j<10;j++)
                    {
                        if (Mini[j-1]< Mini[j])
                        {
                            i++;
                        }
                    } 

                    if (i==9)
                    {
                        Console.WriteLine("SI esta");
                    }
                    else
                    {
                        Console.WriteLine("NO esta");
                    }
                    
                    break;
                case 4:
                    Console.Clear();
                    Console.Write("Clonacion de Números\n");
                    numeros = 0;
                    i = 0;
                    for (int j =0; j<10;j++)
                    {
                        numeros = Mini[j];
                        for (int k =0; k<10;k++)
                        {
                            if (numeros == Mini[k])
                            {
                                i++;
                            }
                        }
                    }
                    if (i > 10)
                    {
                        Console.WriteLine("SI hay numeros repetidos");
                    }
                    else
                    {
                        Console.WriteLine("NO hay numeros repetidos");
                    }

                    break;
                case 5:
                    Console.Clear();
                    Console.Write("Ordenar numeros de menor a mayor");
                    Array.Sort(Mini);
                    Console.WriteLine("\nAsi estaria ordenados de menor a mayor: ");
                    Console.ReadKey();
                    for (int k = 0; k < Mini.Length; k++)
                    {
                        Console.Write(Mini[k].ToString());
                    }
                    break;
                case 6:
                    Console.Clear();
                    //     Console.Write("Profesor, en esta no me dejaba porque soloo buscaria numero ya previamente establecidos" +
                    //       "\npor eso me rendi, esto lo escribo a las 4:16 am)");
                    Console.Write("\nIngrese el numero a comparar \n->");
                    numeros=int.Parse(Console.ReadLine());
                    i = 0;
              
                        for (int k = 0; k < 10; k++)
                        {
                        if (Mini[k]==numeros)
                        {
                            i++;
                        }
                        }
                    if (i>0)
                    {
                        Console.WriteLine("SI esta");
                    }
                    else
                    {
                        Console.WriteLine("NO esta");
                    }
                    break;
                case 7:
                    Console.Clear();
                    Console.Write("Promedio");
                    double sumastodoprimero = 0;
                    foreach (double sumastodo in Mini)
                    {
                        sumastodoprimero += sumastodo;
                    }
                    double divides = sumastodoprimero / Mini.Length;
                    Console.WriteLine("\nPromediando tus números me dio esto: " + divides);
                    break;

            }
            Console.ReadKey();
        }
    }
}
