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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 69e9cab9dda1fefe8bee3dc46b541313d1d80e58
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="53650-102">Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53650-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="53650-103">Eine Assembly oder eine dynamisch gebundene Programmbibliothek (DLL), wird zur Laufzeit mit dem Programm verknüpft.</span><span class="sxs-lookup"><span data-stu-id="53650-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="53650-104">Betrachten Sie das folgende Szenario zur Demonstration erstellen und Verwenden einer DLL:</span><span class="sxs-lookup"><span data-stu-id="53650-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="53650-105">`MathLibrary.DLL`: Die Bibliotheksdatei enthält die Methoden, die zur Laufzeit aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="53650-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="53650-106">In diesem Beispiel enthält die DLL zwei Methoden `Add` und `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="53650-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="53650-107">`Add`: Die Quelldatei mit der Methode `Add`.</span><span class="sxs-lookup"><span data-stu-id="53650-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="53650-108">Es gibt die Summe ihrer Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="53650-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="53650-109">Die Klasse `AddClass` , enthält die Methode `Add` ist ein Mitglied der Namespace `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="53650-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="53650-110">`Mult`: Der Quellcode, der die Methode enthält `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="53650-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="53650-111">Es gibt das Produkt seiner Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="53650-111">It returns the product of its parameters.</span></span> <span data-ttu-id="53650-112">Die Klasse `MultiplyClass` , enthält die Methode `Multiply` ist auch ein Mitglied der Namespace `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="53650-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="53650-113">`TestCode`: Die Datei enthält die `Main` Methode.</span><span class="sxs-lookup"><span data-stu-id="53650-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="53650-114">Die Methoden verwendet zum Berechnen der Summe und das Produkt der Laufzeitargumente in die DLL-Datei.</span><span class="sxs-lookup"><span data-stu-id="53650-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53650-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53650-115">Example</span></span>  
  
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
  
 <span data-ttu-id="53650-116">Diese Datei enthält den Algorithmus, der die DLL-Methoden verwendet `Add` und `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="53650-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="53650-117">Er beginnt mit der Analyse der Argumente über die Befehlszeile `num1` und `num2`.</span><span class="sxs-lookup"><span data-stu-id="53650-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="53650-118">Dann er die Summe berechnet, indem der `Add` Methode für die `AddClass` -Klasse und das Produkt mit der `Multiply` Methode für die `MultiplyClass` Klasse.</span><span class="sxs-lookup"><span data-stu-id="53650-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="53650-119">Beachten Sie, dass die `Imports` -Anweisung am Anfang der Datei können Sie die nicht qualifizierten Klassennamen verwenden, um die DLL-Methoden wie folgt zum Zeitpunkt der Kompilierung zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="53650-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="53650-120">Andernfalls müssen Sie den vollqualifizierten Namen wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="53650-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="53650-121">Ausführung</span><span class="sxs-lookup"><span data-stu-id="53650-121">Execution</span></span>  
 <span data-ttu-id="53650-122">Um das Programm auszuführen, geben Sie den Namen der EXE-Datei, gefolgt von zwei Zahlen, wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="53650-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="53650-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="53650-123">Compiling the Code</span></span>  
 <span data-ttu-id="53650-124">Zum Erstellen der Datei `MathLibrary.DLL`, kompilieren Sie die beiden Dateien `Add` und `Mult` mithilfe der folgenden Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="53650-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```vb  
vbc /target:library /out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 <span data-ttu-id="53650-125">Die [/target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) (Compileroption) teilt dem Compiler mit eine DLL anstelle einer EXE-Datei ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="53650-125">The [/target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="53650-126">Die [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) Compileroption, gefolgt von einem Dateinamen wird verwendet, um den Namen der DLL-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="53650-126">The [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="53650-127">Andernfalls verwendet der Compiler die erste Datei (`Add.vb`) als Name der DLL.</span><span class="sxs-lookup"><span data-stu-id="53650-127">Otherwise, the compiler uses the first file (`Add.vb`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="53650-128">Zum Erstellen der ausführbaren Datei `TestCode.exe`, verwenden Sie die folgende Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="53650-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```vb  
vbc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.vb  
```  
  
 <span data-ttu-id="53650-129">Die **/out** -Compileroption weist den Compiler an, eine EXE-Datei auszugeben, und gibt den Namen der Ausgabedatei (`TestCode.exe`).</span><span class="sxs-lookup"><span data-stu-id="53650-129">The **/out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="53650-130">Diese Compileroption ist optional.</span><span class="sxs-lookup"><span data-stu-id="53650-130">This compiler option is optional.</span></span> <span data-ttu-id="53650-131">Die [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) -Compileroption werden die DLL-Dateien, die von der Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="53650-131">The [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) compiler option specifies the DLL file or files that this program uses.</span></span>  
  
 <span data-ttu-id="53650-132">Weitere Informationen zum Erstellen von der Befehlszeile aus finden Sie unter und [Erstellen von der Befehlszeile aus](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="53650-132">For more information about building from the command line, see  and [Building from the Command Line](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53650-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53650-133">See Also</span></span>  
 <span data-ttu-id="53650-134">[Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="53650-134">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="53650-135"> [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="53650-135"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="53650-136"> [Erstellen einer Klasse zum Halten von DLL-Funktionen](http://msdn.microsoft.com/library/e08e4c34-0223-45f7-aa55-a3d8dd979b0f)</span><span class="sxs-lookup"><span data-stu-id="53650-136"> [Creating a Class to Hold DLL Functions](http://msdn.microsoft.com/library/e08e4c34-0223-45f7-aa55-a3d8dd979b0f)</span></span>
