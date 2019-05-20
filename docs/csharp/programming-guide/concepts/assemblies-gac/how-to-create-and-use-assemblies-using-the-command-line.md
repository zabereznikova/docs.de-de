---
title: 'Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (C#)'
ms.date: 07/20/2015
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
ms.openlocfilehash: 12d23816b740816bd357c3c2ac57583f31bf3cb3
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586034"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="25e2b-102">Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (C#)</span><span class="sxs-lookup"><span data-stu-id="25e2b-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="25e2b-103">Eine Assembly oder eine dynamisch gebundene Programmbibliothek (DLL) wird zur Laufzeit mit dem Programm verknüpft.</span><span class="sxs-lookup"><span data-stu-id="25e2b-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="25e2b-104">Betrachten Sie das folgende Szenario, das die Erstellung und Verwendung einer DLL zeigt:</span><span class="sxs-lookup"><span data-stu-id="25e2b-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
- <span data-ttu-id="25e2b-105">`MathLibrary.DLL`: Die Bibliotheksdatei, die die Methoden enthält, die zur Laufzeit aufgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="25e2b-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="25e2b-106">In diesem Beispiel enthält die DLL zwei Methoden: `Add` und `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="25e2b-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
- <span data-ttu-id="25e2b-107">`Add`: Die Quelldatei, die die Methode `Add` enthält.</span><span class="sxs-lookup"><span data-stu-id="25e2b-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="25e2b-108">Sie gibt die Summe ihrer Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="25e2b-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="25e2b-109">Die Klasse `AddClass`, die die Methode `Add` enthält, gehört zum Namespace `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="25e2b-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="25e2b-110">`Mult`: Der Quellcode, der die Methode `Multiply` enthält.</span><span class="sxs-lookup"><span data-stu-id="25e2b-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="25e2b-111">Er gibt die Summe seiner Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="25e2b-111">It returns the product of its parameters.</span></span> <span data-ttu-id="25e2b-112">Die Klasse `MultiplyClass`, die die Methode `Multiply` enthält, gehört auch zum Namespace `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="25e2b-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="25e2b-113">`TestCode`: Die Datei, die die Methode `Main` enthält.</span><span class="sxs-lookup"><span data-stu-id="25e2b-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="25e2b-114">Sie verwendet in die DLL-Datei Methoden, um die Summe und das Produkt der Laufzeitargumente zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="25e2b-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25e2b-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25e2b-115">Example</span></span>  
  
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
  
 <span data-ttu-id="25e2b-116">Diese Datei enthält den Algorithmus, der die DLL-Methoden `Add` und `Multiply` verwendet.</span><span class="sxs-lookup"><span data-stu-id="25e2b-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="25e2b-117">Zuerst werden die über die Befehlszeile eingegebenen Argumente `num1` und `num2` analysiert.</span><span class="sxs-lookup"><span data-stu-id="25e2b-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="25e2b-118">Anschließend wird die Summe mithilfe der Methode `Add` für die `AddClass`-Klasse und das Produkt mit der Methode `Multiply` für die `MultiplyClass`-Klasse berechnet.</span><span class="sxs-lookup"><span data-stu-id="25e2b-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="25e2b-119">Beachten Sie, dass Sie mit der `using`-Direktive am Anfang der Datei nicht qualifizierte Klassennamen verwenden können, um zum Zeitpunkt der Kompilierung wie folgt auf die DLL-Methoden zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="25e2b-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="25e2b-120">Andernfalls müssen Sie die vollqualifizierten Namen wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="25e2b-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="25e2b-121">Ausführung</span><span class="sxs-lookup"><span data-stu-id="25e2b-121">Execution</span></span>  
 <span data-ttu-id="25e2b-122">Um das Programm auszuführen, geben Sie so den Namen der EXE-Datei gefolgt von zwei Zahlen ein:</span><span class="sxs-lookup"><span data-stu-id="25e2b-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a><span data-ttu-id="25e2b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25e2b-123">See also</span></span>

- [<span data-ttu-id="25e2b-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="25e2b-124">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="25e2b-125">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="25e2b-125">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="25e2b-126">Erstellen einer Klasse zum Halten von DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="25e2b-126">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
