---
title: 'Vorgehensweise: Schreiben einer Erweiterungsmethode (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 31ccb18e0e6d1569764ec2a67201d7f758129425
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332758"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="fabdd-102">Vorgehensweise: Schreiben einer Erweiterungsmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fabdd-102">How to: Write an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="fabdd-103">Erweiterungs Methoden ermöglichen Ihnen das Hinzufügen von Methoden zu einer vorhandenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="fabdd-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="fabdd-104">Die Erweiterungsmethode kann so aufgerufen werden, als ob es sich um eine Instanz dieser Klasse handelt.</span><span class="sxs-lookup"><span data-stu-id="fabdd-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="fabdd-105">So definieren Sie eine Erweiterungsmethode</span><span class="sxs-lookup"><span data-stu-id="fabdd-105">To define an extension method</span></span>

1. <span data-ttu-id="fabdd-106">Öffnen Sie in Visual Studio eine neue oder vorhandene Visual Basic Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fabdd-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="fabdd-107">Fügen Sie am Anfang der Datei, in der Sie eine Erweiterungsmethode definieren möchten, die folgende Import-Anweisung ein:</span><span class="sxs-lookup"><span data-stu-id="fabdd-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="fabdd-108">Beginnen Sie in einem Modul in der neuen oder vorhandenen Anwendung mit der Methoden Definition mit dem Erweiterungs Attribut:</span><span class="sxs-lookup"><span data-stu-id="fabdd-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>

    ```vb
    <Extension()>
    ```

4. <span data-ttu-id="fabdd-109">Deklarieren Sie die Methode auf normale Weise, mit der Ausnahme, dass der Typ des ersten Parameters der Datentyp sein muss, den Sie erweitern möchten.</span><span class="sxs-lookup"><span data-stu-id="fabdd-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="fabdd-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fabdd-110">Example</span></span>

 <span data-ttu-id="fabdd-111">Im folgenden Beispiel wird eine Erweiterungsmethode im-Modul `StringExtensions` deklariert.</span><span class="sxs-lookup"><span data-stu-id="fabdd-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="fabdd-112">Ein zweites Modul, `Module1`, importiert `StringExtensions` und ruft die-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="fabdd-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="fabdd-113">Die Erweiterungsmethode muss sich im Gültigkeitsbereich befinden, wenn Sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fabdd-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="fabdd-114">Erweiterungsmethode `PrintAndPunctuate` erweitert die <xref:System.String>-Klasse mit einer Methode, die die Zeichen folgen Instanz anzeigt, gefolgt von einer Zeichenfolge aus Interpunktions Symbolen, die als Parameter gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fabdd-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>
  
```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

```vb
' Import the module that holds the extension method you want to use,
' and call it.

Imports ConsoleApplication2.StringExtensions

Module Module1
  
    Sub Main()
        Dim example = "Hello"
        example.PrintAndPunctuate("?")
        example.PrintAndPunctuate("!!!!")
    End Sub
    
End Module
```
  
 <span data-ttu-id="fabdd-115">Beachten Sie, dass die-Methode mit zwei Parametern definiert und nur mit einem aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fabdd-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="fabdd-116">Der erste Parameter `aString` in der Methoden Definition ist an `example` gebunden, die Instanz von `String`, die die-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="fabdd-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="fabdd-117">Die Ausgabe des Beispiels sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="fabdd-117">The output of the example is as follows:</span></span>
  
 ```console
 Hello?
 Hello!!!!
 ```
  
## <a name="see-also"></a><span data-ttu-id="fabdd-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fabdd-118">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="fabdd-119">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="fabdd-119">Extension Methods</span></span>](extension-methods.md)
- [<span data-ttu-id="fabdd-120">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fabdd-120">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="fabdd-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="fabdd-121">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fabdd-122">Bereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fabdd-122">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
