---
title: 'Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (Visual Basic)'
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: eecd644a7b91492f0a78cf969cfa71ae927609ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819399"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="1bb37-102">Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bb37-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="1bb37-103">Eine Assembly oder eine dynamisch gebundene Programmbibliothek (DLL) wird zur Laufzeit mit dem Programm verknüpft.</span><span class="sxs-lookup"><span data-stu-id="1bb37-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="1bb37-104">Betrachten Sie das folgende Szenario, das die Erstellung und Verwendung einer DLL zeigt:</span><span class="sxs-lookup"><span data-stu-id="1bb37-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="1bb37-105">`MathLibrary.DLL`: Die Bibliotheksdatei, die die Methoden enthält, die zur Laufzeit aufgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1bb37-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="1bb37-106">In diesem Beispiel enthält die DLL zwei Methoden: `Add` und `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="1bb37-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="1bb37-107">`Add`: Die Quelldatei, die die Methode `Add` enthält.</span><span class="sxs-lookup"><span data-stu-id="1bb37-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="1bb37-108">Sie gibt die Summe ihrer Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="1bb37-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="1bb37-109">Die Klasse `AddClass`, die die Methode `Add` enthält, gehört zum Namespace `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="1bb37-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="1bb37-110">`Mult`: Der Quellcode, der die Methode `Multiply` enthält.</span><span class="sxs-lookup"><span data-stu-id="1bb37-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="1bb37-111">Er gibt die Summe seiner Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="1bb37-111">It returns the product of its parameters.</span></span> <span data-ttu-id="1bb37-112">Die Klasse `MultiplyClass`, die die Methode `Multiply` enthält, gehört auch zum Namespace `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="1bb37-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="1bb37-113">`TestCode`: Die Datei, die die Methode `Main` enthält.</span><span class="sxs-lookup"><span data-stu-id="1bb37-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="1bb37-114">Sie verwendet in die DLL-Datei Methoden, um die Summe und das Produkt der Laufzeitargumente zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="1bb37-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bb37-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1bb37-115">Example</span></span>  
  
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
  
 <span data-ttu-id="1bb37-116">Diese Datei enthält den Algorithmus, der die DLL-Methoden `Add` und `Multiply` verwendet.</span><span class="sxs-lookup"><span data-stu-id="1bb37-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="1bb37-117">Zuerst werden die über die Befehlszeile eingegebenen Argumente `num1` und `num2` analysiert.</span><span class="sxs-lookup"><span data-stu-id="1bb37-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="1bb37-118">Anschließend wird die Summe mithilfe der Methode `Add` für die `AddClass`-Klasse und das Produkt mit der Methode `Multiply` für die `MultiplyClass`-Klasse berechnet.</span><span class="sxs-lookup"><span data-stu-id="1bb37-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="1bb37-119">Beachten Sie, dass die `Imports` -Anweisung am Anfang der Datei können Sie nicht qualifizierte Klassennamen verwenden, um die DLL-Methoden wie folgt zum Zeitpunkt der Kompilierung zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="1bb37-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="1bb37-120">Andernfalls müssen Sie die vollqualifizierten Namen wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="1bb37-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="1bb37-121">Ausführung</span><span class="sxs-lookup"><span data-stu-id="1bb37-121">Execution</span></span>  
 <span data-ttu-id="1bb37-122">Um das Programm auszuführen, geben Sie so den Namen der EXE-Datei gefolgt von zwei Zahlen ein:</span><span class="sxs-lookup"><span data-stu-id="1bb37-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1bb37-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1bb37-123">Compiling the Code</span></span>  
 <span data-ttu-id="1bb37-124">Um die Datei `MathLibrary.DLL` zu erstellen, kompilieren Sie die beiden Dateien `Add` und `Mult` mithilfe der folgenden Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="1bb37-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```console  
vbc -target:library -out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 <span data-ttu-id="1bb37-125">Die [-Target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) -Compileroption informiert den Compiler, eine DLL-statt einer EXE-Datei auszugeben.</span><span class="sxs-lookup"><span data-stu-id="1bb37-125">The [-target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="1bb37-126">Die [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) Compileroption, gefolgt von einem Dateinamen wird verwendet, um den Namen der DLL anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1bb37-126">The [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="1bb37-127">Andernfalls verwendet der Compiler die erste Datei (`Add.vb`) als Name der DLL.</span><span class="sxs-lookup"><span data-stu-id="1bb37-127">Otherwise, the compiler uses the first file (`Add.vb`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="1bb37-128">Um die ausführbare Datei `TestCode.exe` zu erstellen, verwenden Sie die folgende Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="1bb37-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```console  
vbc -out:TestCode.exe -reference:MathLibrary.DLL TestCode.vb  
```  
  
 <span data-ttu-id="1bb37-129">Die **-out** Compiler-Option weist den Compiler, eine EXE-Datei auszugeben, und gibt den Namen der Ausgabedatei (`TestCode.exe`).</span><span class="sxs-lookup"><span data-stu-id="1bb37-129">The **-out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="1bb37-130">Diese Compileroption ist optional.</span><span class="sxs-lookup"><span data-stu-id="1bb37-130">This compiler option is optional.</span></span> <span data-ttu-id="1bb37-131">Die [-Referenz (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) Compileroption gibt an, die DLL-Dateien, die dieses Programm verwendet.</span><span class="sxs-lookup"><span data-stu-id="1bb37-131">The [-reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) compiler option specifies the DLL file or files that this program uses.</span></span>  
  
 <span data-ttu-id="1bb37-132">Weitere Informationen zum Erstellen von Builds über die Befehlszeile finden Sie unter und [erstellen über die Befehlszeile](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="1bb37-132">For more information about building from the command line, see  and [Building from the Command Line](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb37-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1bb37-133">See also</span></span>

- [<span data-ttu-id="1bb37-134">Programmierkonzepte</span><span class="sxs-lookup"><span data-stu-id="1bb37-134">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="1bb37-135">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="1bb37-135">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="1bb37-136">Erstellen einer Klasse zum Halten von DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="1bb37-136">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
