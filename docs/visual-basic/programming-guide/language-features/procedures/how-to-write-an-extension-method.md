---
title: 'Gewusst wie: Schreiben einer Erweiterungsmethode (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 4671728330614f0f3da23fd90f5e635ddcf46578
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581155"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="61b17-102">Gewusst wie: Schreiben einer Erweiterungsmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61b17-102">How to: Write an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="61b17-103">Erweiterungs Methoden ermöglichen Ihnen das Hinzufügen von Methoden zu einer vorhandenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="61b17-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="61b17-104">Die Erweiterungsmethode kann so aufgerufen werden, als ob es sich um eine Instanz dieser Klasse handelt.</span><span class="sxs-lookup"><span data-stu-id="61b17-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="61b17-105">So definieren Sie eine Erweiterungsmethode</span><span class="sxs-lookup"><span data-stu-id="61b17-105">To define an extension method</span></span>

1. <span data-ttu-id="61b17-106">Öffnen Sie in Visual Studio eine neue oder vorhandene Visual Basic Anwendung.</span><span class="sxs-lookup"><span data-stu-id="61b17-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="61b17-107">Fügen Sie am Anfang der Datei, in der Sie eine Erweiterungsmethode definieren möchten, die folgende Import-Anweisung ein:</span><span class="sxs-lookup"><span data-stu-id="61b17-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="61b17-108">Beginnen Sie in einem Modul in der neuen oder vorhandenen Anwendung mit der-Methoden Definition mit dem [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) -Attribut:</span><span class="sxs-lookup"><span data-stu-id="61b17-108">Within a module in your new or existing application, begin the method definition with the [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) attribute:</span></span>

    ```vb
    <Extension()>
    ```

    <span data-ttu-id="61b17-109">Beachten Sie, dass das `Extension`-Attribut in einem Visual Basic [Modul](../../../language-reference/statements/module-statement.md)nur auf eine Methode (eine `Sub` oder `Function` Prozedur) angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="61b17-109">Note that the `Extension` attribute can only be applied to a method (a `Sub` or `Function` procedure) in a Visual Basic [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="61b17-110">Wenn Sie es auf eine Methode in einer `Class` oder `Structure` anwenden, generiert der Visual Basic-Compiler den Fehler [BC36551](../../../misc/bc36551.md), "Erweiterungs Methoden können nur in Modulen definiert werden."</span><span class="sxs-lookup"><span data-stu-id="61b17-110">If you apply it to a method in a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules."</span></span>

4. <span data-ttu-id="61b17-111">Deklarieren Sie die Methode auf normale Weise, mit der Ausnahme, dass der Typ des ersten Parameters der Datentyp sein muss, den Sie erweitern möchten.</span><span class="sxs-lookup"><span data-stu-id="61b17-111">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="61b17-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61b17-112">Example</span></span>

<span data-ttu-id="61b17-113">Im folgenden Beispiel wird eine Erweiterungsmethode im Modul `StringExtensions` deklariert.</span><span class="sxs-lookup"><span data-stu-id="61b17-113">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="61b17-114">Ein zweites Modul, `Module1`, importiert `StringExtensions` und ruft die-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="61b17-114">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="61b17-115">Die Erweiterungsmethode muss sich im Gültigkeitsbereich befinden, wenn Sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="61b17-115">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="61b17-116">Erweiterungsmethode `PrintAndPunctuate` erweitert die <xref:System.String>-Klasse mit einer Methode, die die Zeichen folgen Instanz anzeigt, gefolgt von einer Zeichenfolge aus Interpunktions Symbolen, die als Parameter gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="61b17-116">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>

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

<span data-ttu-id="61b17-117">Beachten Sie, dass die-Methode mit zwei Parametern definiert und nur mit einem aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="61b17-117">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="61b17-118">Der erste Parameter `aString` in der Methoden Definition ist an `example` gebunden, d. h. die Instanz von `String`, die die-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="61b17-118">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="61b17-119">Die Ausgabe des Beispiels sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="61b17-119">The output of the example is as follows:</span></span>

```console
Hello?
Hello!!!!
```

## <a name="see-also"></a><span data-ttu-id="61b17-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61b17-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="61b17-121">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="61b17-121">Extension Methods</span></span>](extension-methods.md)
- [<span data-ttu-id="61b17-122">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="61b17-122">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="61b17-123">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="61b17-123">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="61b17-124">Bereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="61b17-124">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
