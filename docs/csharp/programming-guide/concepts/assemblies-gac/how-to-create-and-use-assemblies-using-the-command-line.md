---
title: "Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (C#) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: fc55d0ead04897f967d8cfe767e0a79f3469427c
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a>Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (C#)
Eine Assembly oder eine dynamisch gebundene Programmbibliothek (DLL) wird zur Laufzeit mit dem Programm verknüpft. Betrachten Sie das folgende Szenario, das die Erstellung und Verwendung einer DLL zeigt:  
  
-   `MathLibrary.DLL`: Die Bibliotheksdatei enthält die Methoden, die zur Laufzeit aufgerufen werden sollen. In diesem Beispiel enthält die DLL zwei Methoden: `Add` und `Multiply`.  
  
-   `Add`: Die Quelldatei, die die Methode `Add` enthält. Sie gibt die Summe ihrer Parameter zurück. Die Klasse `AddClass`, die die Methode `Add` enthält, gehört zum Namespace `UtilityMethods`.  
  
-   `Mult`: Der Quellcode, der die Methode `Multiply` enthält. Er gibt die Summe seiner Parameter zurück. Die Klasse `MultiplyClass`, die die Methode `Multiply` enthält, gehört auch zum Namespace `UtilityMethods`.  
  
-   `TestCode`: Die Datei, die die Methode `Main` enthält. Sie verwendet in die DLL-Datei Methoden, um die Summe und das Produkt der Laufzeitargumente zu berechnen.  
  
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
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um die Datei `MathLibrary.DLL` zu erstellen, kompilieren Sie die beiden Dateien `Add` und `Mult` mithilfe der folgenden Befehlszeile.  
  
```csharp  
csc /target:library /out:MathLibrary.DLL Add.cs Mult.cs  
```  
  
 Die Compileroption [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) weist den Compiler an, eine DLL- statt einer EXE-Datei auszugeben. Die Compileroption [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) wird gefolgt von einem Dateinamen verwendet, um den Namen der DLL-Datei anzugeben. Andernfalls verwendet der Compiler die erste Datei (`Add.cs`) als Name der DLL.  
  
 Um die ausführbare Datei `TestCode.exe` zu erstellen, verwenden Sie die folgende Befehlszeile:  
  
```csharp  
csc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.cs  
```  
  
 Die Compileroption **/out** weist den Compiler an, eine EXE-Datei auszugeben, und gibt den Namen der Ausgabedatei (`TestCode.exe`) an. Diese Compileroption ist optional. Die Compileroption [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) gibt die von diesem Programm verwendeten DLL-Dateien an. Weitere Informationen finden Sie unter [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).  
  
 Weitere Informationen zum Erstellen über die Befehlszeile finden Sie unter [Erstellen über die Befehlszeile mit csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)   
 [Assemblys und der globale Assemblycache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)   
 [Erstellen einer Klasse zum Halten von DLL-Funktionen](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
