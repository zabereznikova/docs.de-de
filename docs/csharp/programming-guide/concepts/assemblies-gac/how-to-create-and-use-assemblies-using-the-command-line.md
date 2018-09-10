---
title: 'Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (C#)'
ms.date: 07/20/2015
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
ms.openlocfilehash: 0cb964991cdbcdb3fa528ac96a0e883a37439099
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514554"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="de82e-102">Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (C#)</span><span class="sxs-lookup"><span data-stu-id="de82e-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="de82e-103">Eine Assembly oder eine dynamisch gebundene Programmbibliothek (DLL) wird zur Laufzeit mit dem Programm verknüpft.</span><span class="sxs-lookup"><span data-stu-id="de82e-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="de82e-104">Betrachten Sie das folgende Szenario, das die Erstellung und Verwendung einer DLL zeigt:</span><span class="sxs-lookup"><span data-stu-id="de82e-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="de82e-105">`MathLibrary.DLL`: Die Bibliotheksdatei enthält die Methoden, die zur Laufzeit aufgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="de82e-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="de82e-106">In diesem Beispiel enthält die DLL zwei Methoden: `Add` und `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="de82e-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="de82e-107">`Add`: Die Quelldatei, die die Methode `Add` enthält.</span><span class="sxs-lookup"><span data-stu-id="de82e-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="de82e-108">Sie gibt die Summe ihrer Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="de82e-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="de82e-109">Die Klasse `AddClass`, die die Methode `Add` enthält, gehört zum Namespace `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="de82e-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="de82e-110">`Mult`: Der Quellcode, der die Methode `Multiply` enthält.</span><span class="sxs-lookup"><span data-stu-id="de82e-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="de82e-111">Er gibt die Summe seiner Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="de82e-111">It returns the product of its parameters.</span></span> <span data-ttu-id="de82e-112">Die Klasse `MultiplyClass`, die die Methode `Multiply` enthält, gehört auch zum Namespace `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="de82e-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="de82e-113">`TestCode`: Die Datei, die die Methode `Main` enthält.</span><span class="sxs-lookup"><span data-stu-id="de82e-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="de82e-114">Sie verwendet in die DLL-Datei Methoden, um die Summe und das Produkt der Laufzeitargumente zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="de82e-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de82e-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de82e-115">Example</span></span>  
  
```csharp  
// File: Add.cs   
namespace UtilityMethods  
{  
    public class AddClass   
    {  
        public static long Add(long i, long j)   
        {   
            return (i + j);  
        }  
    }  
}  
```  
  
```csharp  
// File: Mult.cs  
namespace UtilityMethods   
{  
    public class MultiplyClass  
    {  
        public static long Multiply(long x, long y)   
        {  
            return (x * y);   
        }  
    }  
}  
```  
  
```csharp  
// File: TestCode.cs  
  
using UtilityMethods;  
  
class TestCode  
{  
    static void Main(string[] args)   
    {  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:");  
  
        if (args.Length != 2)  
        {  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>");  
            return;  
        }  
  
        long num1 = long.Parse(args[0]);  
        long num2 = long.Parse(args[1]);  
  
        long sum = AddClass.Add(num1, num2);  
        long product = MultiplyClass.Multiply(num1, num2);  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum);  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product);  
    }  
}  
/* Output (assuming 1234 and 5678 are entered as command-line arguments):  
    Calling methods from MathLibrary.DLL:  
    1234 + 5678 = 6912  
    1234 * 5678 = 7006652          
*/  
```  
  
 <span data-ttu-id="de82e-116">Diese Datei enthält den Algorithmus, der die DLL-Methoden `Add` und `Multiply` verwendet.</span><span class="sxs-lookup"><span data-stu-id="de82e-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="de82e-117">Zuerst werden die über die Befehlszeile eingegebenen Argumente `num1` und `num2` analysiert.</span><span class="sxs-lookup"><span data-stu-id="de82e-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="de82e-118">Anschließend wird die Summe mithilfe der Methode `Add` für die `AddClass`-Klasse und das Produkt mit der Methode `Multiply` für die `MultiplyClass`-Klasse berechnet.</span><span class="sxs-lookup"><span data-stu-id="de82e-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="de82e-119">Beachten Sie, dass Sie mit der `using`-Direktive am Anfang der Datei nicht qualifizierte Klassennamen verwenden können, um zum Zeitpunkt der Kompilierung wie folgt auf die DLL-Methoden zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="de82e-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="de82e-120">Andernfalls müssen Sie die vollqualifizierten Namen wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="de82e-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="de82e-121">Ausführung</span><span class="sxs-lookup"><span data-stu-id="de82e-121">Execution</span></span>  
 <span data-ttu-id="de82e-122">Um das Programm auszuführen, geben Sie so den Namen der EXE-Datei gefolgt von zwei Zahlen ein:</span><span class="sxs-lookup"><span data-stu-id="de82e-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="de82e-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="de82e-123">Compiling the Code</span></span>  
 <span data-ttu-id="de82e-124">Um die Datei `MathLibrary.DLL` zu erstellen, kompilieren Sie die beiden Dateien `Add` und `Mult` mithilfe der folgenden Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="de82e-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```csharp  
csc /target:library /out:MathLibrary.DLL Add.cs Mult.cs  
```  
  
 <span data-ttu-id="de82e-125">Die Compileroption [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) weist den Compiler an, eine DLL- statt einer EXE-Datei auszugeben.</span><span class="sxs-lookup"><span data-stu-id="de82e-125">The [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="de82e-126">Die Compileroption [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) wird gefolgt von einem Dateinamen verwendet, um den Namen der DLL-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="de82e-126">The [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="de82e-127">Andernfalls verwendet der Compiler die erste Datei (`Add.cs`) als Name der DLL.</span><span class="sxs-lookup"><span data-stu-id="de82e-127">Otherwise, the compiler uses the first file (`Add.cs`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="de82e-128">Um die ausführbare Datei `TestCode.exe` zu erstellen, verwenden Sie die folgende Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="de82e-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```csharp  
csc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.cs  
```  
  
 <span data-ttu-id="de82e-129">Die Compileroption **/out** weist den Compiler an, eine EXE-Datei auszugeben, und gibt den Namen der Ausgabedatei (`TestCode.exe`) an.</span><span class="sxs-lookup"><span data-stu-id="de82e-129">The **/out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="de82e-130">Diese Compileroption ist optional.</span><span class="sxs-lookup"><span data-stu-id="de82e-130">This compiler option is optional.</span></span> <span data-ttu-id="de82e-131">Die Compileroption [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) gibt die von diesem Programm verwendeten DLL-Dateien an.</span><span class="sxs-lookup"><span data-stu-id="de82e-131">The [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option specifies the DLL file or files that this program uses.</span></span> <span data-ttu-id="de82e-132">Weitere Informationen finden Sie unter [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="de82e-132">For more information, see [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="de82e-133">Weitere Informationen zum Erstellen über die Befehlszeile finden Sie unter [Erstellen über die Befehlszeile mit csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="de82e-133">For more information about building from the command line, see [Command-line Building With csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de82e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de82e-134">See Also</span></span>

- [<span data-ttu-id="de82e-135">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="de82e-135">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="de82e-136">Assemblies and the Global Assembly Cache (C#) (Assemblys und der globale Assemblycache (C#))</span><span class="sxs-lookup"><span data-stu-id="de82e-136">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
- [<span data-ttu-id="de82e-137">Erstellen einer Klasse zum Halten von DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="de82e-137">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
