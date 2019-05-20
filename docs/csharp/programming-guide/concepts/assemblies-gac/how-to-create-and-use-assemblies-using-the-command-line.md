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
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a>Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (C#)
Eine Assembly oder eine dynamisch gebundene Programmbibliothek (DLL) wird zur Laufzeit mit dem Programm verknüpft. Betrachten Sie das folgende Szenario, das die Erstellung und Verwendung einer DLL zeigt:  
  
- `MathLibrary.DLL`: Die Bibliotheksdatei, die die Methoden enthält, die zur Laufzeit aufgerufen werden sollen. In diesem Beispiel enthält die DLL zwei Methoden: `Add` und `Multiply`.  
  
- `Add`: Die Quelldatei, die die Methode `Add` enthält. Sie gibt die Summe ihrer Parameter zurück. Die Klasse `AddClass`, die die Methode `Add` enthält, gehört zum Namespace `UtilityMethods`.  
  
- `Mult`: Der Quellcode, der die Methode `Multiply` enthält. Er gibt die Summe seiner Parameter zurück. Die Klasse `MultiplyClass`, die die Methode `Multiply` enthält, gehört auch zum Namespace `UtilityMethods`.  
  
- `TestCode`: Die Datei, die die Methode `Main` enthält. Sie verwendet in die DLL-Datei Methoden, um die Summe und das Produkt der Laufzeitargumente zu berechnen.  
  
## <a name="example"></a>Beispiel  
  
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
  
 Diese Datei enthält den Algorithmus, der die DLL-Methoden `Add` und `Multiply` verwendet. Zuerst werden die über die Befehlszeile eingegebenen Argumente `num1` und `num2` analysiert. Anschließend wird die Summe mithilfe der Methode `Add` für die `AddClass`-Klasse und das Produkt mit der Methode `Multiply` für die `MultiplyClass`-Klasse berechnet.  
  
 Beachten Sie, dass Sie mit der `using`-Direktive am Anfang der Datei nicht qualifizierte Klassennamen verwenden können, um zum Zeitpunkt der Kompilierung wie folgt auf die DLL-Methoden zu verweisen:  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 Andernfalls müssen Sie die vollqualifizierten Namen wie folgt verwenden:  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a>Ausführung  
 Um das Programm auszuführen, geben Sie so den Namen der EXE-Datei gefolgt von zwei Zahlen ein:  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)
- [Assemblys in .NET](../../../../standard/assembly/index.md)
- [Erstellen einer Klasse zum Halten von DLL-Funktionen](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
