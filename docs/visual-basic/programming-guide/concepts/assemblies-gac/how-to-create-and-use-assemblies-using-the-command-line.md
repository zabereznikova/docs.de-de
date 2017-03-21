---
title: "Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 363bca806736e5540165ea96e9b4fe60d0968098
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile (Visual Basic)
Eine Assembly oder eine dynamisch gebundene Programmbibliothek (DLL), wird zur Laufzeit mit dem Programm verknüpft. Betrachten Sie das folgende Szenario zur Demonstration erstellen und Verwenden einer DLL:  
  
-   `MathLibrary.DLL`: Die Bibliotheksdatei enthält die Methoden, die zur Laufzeit aufgerufen werden. In diesem Beispiel enthält die DLL zwei Methoden `Add` und `Multiply`.  
  
-   `Add`: Die Quelldatei mit der Methode `Add`. Es gibt die Summe ihrer Parameter zurück. Die Klasse `AddClass` , enthält die Methode `Add` ist ein Mitglied der Namespace `UtilityMethods`.  
  
-   `Mult`: Der Quellcode, der die Methode enthält `Multiply`. Es gibt das Produkt seiner Parameter zurück. Die Klasse `MultiplyClass` , enthält die Methode `Multiply` ist auch ein Mitglied der Namespace `UtilityMethods`.  
  
-   `TestCode`: Die Datei enthält die `Main` Methode. Die Methoden verwendet zum Berechnen der Summe und das Produkt der Laufzeitargumente in die DLL-Datei.  
  
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
  
 Diese Datei enthält den Algorithmus, der die DLL-Methoden verwendet `Add` und `Multiply`. Er beginnt mit der Analyse der Argumente über die Befehlszeile `num1` und `num2`. Dann er die Summe berechnet, indem der `Add` Methode für die `AddClass` -Klasse und das Produkt mit der `Multiply` Methode für die `MultiplyClass` Klasse.  
  
 Beachten Sie, dass die `Imports` -Anweisung am Anfang der Datei können Sie die nicht qualifizierten Klassennamen verwenden, um die DLL-Methoden wie folgt zum Zeitpunkt der Kompilierung zu verweisen:  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 Andernfalls müssen Sie den vollqualifizierten Namen wie folgt verwenden:  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>Ausführung  
 Um das Programm auszuführen, geben Sie den Namen der EXE-Datei, gefolgt von zwei Zahlen, wie folgt aus:  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Zum Erstellen der Datei `MathLibrary.DLL`, kompilieren Sie die beiden Dateien `Add` und `Mult` mithilfe der folgenden Befehlszeile aus.  
  
```vb  
vbc /target:library /out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 Die [/target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) (Compileroption) teilt dem Compiler mit eine DLL anstelle einer EXE-Datei ausgegeben. Die [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) Compileroption, gefolgt von einem Dateinamen wird verwendet, um den Namen der DLL-Datei angeben. Andernfalls verwendet der Compiler die erste Datei (`Add.vb`) als Name der DLL.  
  
 Zum Erstellen der ausführbaren Datei `TestCode.exe`, verwenden Sie die folgende Befehlszeile:  
  
```vb  
vbc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.vb  
```  
  
 Die **/out** -Compileroption weist den Compiler an, eine EXE-Datei auszugeben, und gibt den Namen der Ausgabedatei (`TestCode.exe`). Diese Compileroption ist optional. Die [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) -Compileroption werden die DLL-Dateien, die von der Anwendung verwendet.  
  
 Weitere Informationen zum Erstellen von der Befehlszeile aus finden Sie unter und [Erstellen von der Befehlszeile aus](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)   
 [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Erstellen einer Klasse zum Halten von DLL-Funktionen](http://msdn.microsoft.com/library/e08e4c34-0223-45f7-aa55-a3d8dd979b0f)
