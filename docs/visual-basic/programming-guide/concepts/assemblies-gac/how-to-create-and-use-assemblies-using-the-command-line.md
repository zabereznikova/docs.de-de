---
title: 'Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (Visual Basic)'
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: a30d4b3ea203a8b4d3ba621fc7b0310477ddf10d
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592685"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (Visual Basic)
Eine Assembly oder eine dynamisch gebundene Programmbibliothek (DLL) wird zur Laufzeit mit dem Programm verknüpft. Betrachten Sie das folgende Szenario, das die Erstellung und Verwendung einer DLL zeigt:  
  
- `MathLibrary.DLL`: Die Bibliotheksdatei, die die Methoden enthält, die zur Laufzeit aufgerufen werden sollen. In diesem Beispiel enthält die DLL zwei Methoden: `Add` und `Multiply`.  
  
- `Add`: Die Quelldatei, die die Methode `Add` enthält. Sie gibt die Summe ihrer Parameter zurück. Die Klasse `AddClass`, die die Methode `Add` enthält, gehört zum Namespace `UtilityMethods`.  
  
- `Mult`: Der Quellcode, der die Methode `Multiply` enthält. Er gibt die Summe seiner Parameter zurück. Die Klasse `MultiplyClass`, die die Methode `Multiply` enthält, gehört auch zum Namespace `UtilityMethods`.  
  
- `TestCode`: Die Datei, die die Methode `Main` enthält. Sie verwendet in die DLL-Datei Methoden, um die Summe und das Produkt der Laufzeitargumente zu berechnen.  
  
## <a name="example"></a>Beispiel  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 Diese Datei enthält den Algorithmus, der die DLL-Methoden `Add` und `Multiply` verwendet. Zuerst werden die über die Befehlszeile eingegebenen Argumente `num1` und `num2` analysiert. Anschließend wird die Summe mithilfe der Methode `Add` für die `AddClass`-Klasse und das Produkt mit der Methode `Multiply` für die `MultiplyClass`-Klasse berechnet.  
  
 Beachten Sie, dass die `Imports` -Anweisung am Anfang der Datei können Sie nicht qualifizierte Klassennamen verwenden, um die DLL-Methoden wie folgt zum Zeitpunkt der Kompilierung zu verweisen:  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 Andernfalls müssen Sie die vollqualifizierten Namen wie folgt verwenden:  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>Ausführung  
 Um das Programm auszuführen, geben Sie so den Namen der EXE-Datei gefolgt von zwei Zahlen ein:  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a>Siehe auch

- [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)
- [Assemblys in .NET](../../../../standard/assembly/index.md)
- [Erstellen einer Klasse zum Halten von DLL-Funktionen](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
