# una-ihcux-lista05

using System;
using System.Threading;

class Program
{
    static void Main()
    {
        // --- Interface inicial ---
        Console.Clear();
        Console.ForegroundColor = ConsoleColor.Yellow;
        Console.WriteLine("=======================================");
        Console.WriteLine("   GLOBAL EXCHANGE - CONVERSOR v1.0   ");
        Console.WriteLine("=======================================");
        Console.ResetColor();

        try
        {
            // --- Entrada de dados ---
            Console.Write("\nDigite o valor em REAIS (R$): ");
            string entrada = Console.ReadLine();
            double valorReais = double.Parse(entrada);

            Console.Write("Digite a cotação do DÓLAR (ex: 5.20): ");
            double cotacaoDolar = double.Parse(Console.ReadLine());

            // --- Feedback (UX) ---
            Console.WriteLine("\n[SISTEMA]: Conectando ao Banco Central...");
            Thread.Sleep(1000);

            Console.Write("[SISTEMA]: Calculando taxas");
            for (int i = 0; i < 3; i++)
            {
                Thread.Sleep(500);
                Console.Write(".");
            }

            // --- Cálculo ---
            double resultado = valorReais / cotacaoDolar;

            // --- Saída bonita ---
            Console.ForegroundColor = ConsoleColor.Green;
            Console.WriteLine($"\n\nVALOR CONVERTIDO: $ {resultado:F2} dólares");
            Console.WriteLine("=======================================");
            Console.ResetColor();
        }
        catch (FormatException)
        {
            Console.ForegroundColor = ConsoleColor.Red;
            Console.WriteLine("\nErro: digite apenas números válidos!");
            Console.WriteLine("Exemplo: 10 ou 5.20");
            Console.ResetColor();
        }
        catch (Exception)
        {
            Console.ForegroundColor = ConsoleColor.Red;
            Console.WriteLine("\nErro inesperado. Tente novamente.");
            Console.ResetColor();
        }

        Console.WriteLine("\nPressione qualquer tecla para sair...");
        Console.ReadKey();
    }
}

(https://github.com/user-attachments/assets/b0555f10-25b3-4382-8688-8b176b983752)
