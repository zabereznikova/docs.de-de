---
title: 'Gewusst wie: Aufrufen einer Erweiterungsmethode'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: a19705a8f90833d48869df26a18d19b0ad1488e0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340399"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="b1aa7-102">Gewusst wie: Aufrufen einer Erweiterungsmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1aa7-102">How to: Call an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="b1aa7-103">Erweiterungs Methoden ermöglichen Ihnen das Hinzufügen von Methoden zu einer vorhandenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="b1aa7-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="b1aa7-104">Nachdem eine Erweiterungsmethode deklariert und in den Gültigkeitsbereich eingefügt wurde, können Sie Sie wie eine Instanzmethode des Typs, der Sie erweitert, abrufen.</span><span class="sxs-lookup"><span data-stu-id="b1aa7-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="b1aa7-105">Weitere Informationen zum Schreiben einer Erweiterungsmethode finden Sie unter Gewusst [wie: Schreiben einer Erweiterungsmethode](./how-to-write-an-extension-method.md).</span><span class="sxs-lookup"><span data-stu-id="b1aa7-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>

 <span data-ttu-id="b1aa7-106">Die folgenden Anweisungen beziehen sich auf die Erweiterungsmethode `PrintAndPunctuate`, die die Zeichen folgen Instanz anzeigt, die diese aufruft, gefolgt von dem Wert, der für den zweiten Parameter, `punc`, gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="b1aa7-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>

```vb
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

<span data-ttu-id="b1aa7-107">Die Methode muss sich im Gültigkeitsbereich befinden, wenn Sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b1aa7-107">The method must be in scope when it is called.</span></span>

### <a name="to-call-an-extension-method"></a><span data-ttu-id="b1aa7-108">So greifen Sie auf eine Erweiterungsmethode zu</span><span class="sxs-lookup"><span data-stu-id="b1aa7-108">To call an extension method</span></span>

1. <span data-ttu-id="b1aa7-109">Deklarieren Sie eine Variable, die den Datentyp des ersten Parameters der Erweiterungsmethode aufweist.</span><span class="sxs-lookup"><span data-stu-id="b1aa7-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="b1aa7-110">Für `PrintAndPunctuate`benötigen Sie eine <xref:System.String> Variable:</span><span class="sxs-lookup"><span data-stu-id="b1aa7-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>

    ```vb
    Dim example = "Ready"
    ```

2. <span data-ttu-id="b1aa7-111">Diese Variable Ruft die Erweiterungsmethode auf, und ihr Wert wird an den ersten Parameter, `aString`, gebunden.</span><span class="sxs-lookup"><span data-stu-id="b1aa7-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="b1aa7-112">Mit der folgenden aufrufenden Anweisung wird `Ready?`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1aa7-112">The following calling statement will display `Ready?`.</span></span>

    ```vb
    example.PrintAndPunctuate("?")
    ```

     <span data-ttu-id="b1aa7-113">Beachten Sie, dass der Aufrufen dieser Erweiterungsmethode genau wie ein Aufrufen einer der <xref:System.String> Instanzmethoden aussieht, die einen Parameter erfordern:</span><span class="sxs-lookup"><span data-stu-id="b1aa7-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. <span data-ttu-id="b1aa7-114">Deklarieren Sie eine weitere Zeichen folgen Variable, und rufen Sie die Methode erneut auf, um zu überprüfen, ob Sie mit</span><span class="sxs-lookup"><span data-stu-id="b1aa7-114">Declare another string variable and call the method again to see that it works with any string.</span></span>

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     <span data-ttu-id="b1aa7-115">Das Ergebnis ist dieses Mal: `or not!!!`.</span><span class="sxs-lookup"><span data-stu-id="b1aa7-115">The result this time is: `or not!!!`.</span></span>

## <a name="example"></a><span data-ttu-id="b1aa7-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1aa7-116">Example</span></span>
 <span data-ttu-id="b1aa7-117">Der folgende Code ist ein umfassendes Beispiel für die Erstellung und Verwendung einer einfachen Erweiterungsmethode.</span><span class="sxs-lookup"><span data-stu-id="b1aa7-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>

```vb
Imports System.Runtime.CompilerServices
Imports ConsoleApplication1.StringExtensions

Module Module1

    Sub Main()

        Dim example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")

        Dim example2 = "Goodbye"
        example2.PrintAndPunctuate("?")
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module

' Output:
' Hello.
' Hello!!!!
' Goodbye?
```

## <a name="see-also"></a><span data-ttu-id="b1aa7-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1aa7-118">See also</span></span>

- [<span data-ttu-id="b1aa7-119">Gewusst wie: Schreiben einer Erweiterungsmethode</span><span class="sxs-lookup"><span data-stu-id="b1aa7-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="b1aa7-120">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="b1aa7-120">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="b1aa7-121">Bereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1aa7-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
