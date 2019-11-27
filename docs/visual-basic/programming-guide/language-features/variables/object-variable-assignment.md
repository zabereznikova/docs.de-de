---
title: Zuweisen von Objektvariablen
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: 93de17490935d6d5cad01000e9ee3e2fe55bd16c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351820"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="16c4a-102">Zuweisen von Objektvariablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16c4a-102">Object Variable Assignment (Visual Basic)</span></span>

<span data-ttu-id="16c4a-103">Sie verwenden eine normale Zuweisungsanweisung, um ein Objekt einer Objektvariablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="16c4a-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="16c4a-104">Sie können einen Objekt Ausdruck oder das [Nothing](../../../../visual-basic/language-reference/nothing.md) -Schlüsselwort zuweisen, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="16c4a-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>

```vb
Dim thisObject As Object
' The following statement assigns an object reference.
thisObject = Form1
' The following statement discontinues association with any object.
thisObject = Nothing
```

<span data-ttu-id="16c4a-105">`Nothing` bedeutet, dass der Variablen zurzeit kein-Objekt zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="16c4a-105">`Nothing` means there is no object currently assigned to the variable.</span></span>

## <a name="initialization"></a><span data-ttu-id="16c4a-106">Initialisierung</span><span class="sxs-lookup"><span data-stu-id="16c4a-106">Initialization</span></span>

<span data-ttu-id="16c4a-107">Wenn Ihr Code gestartet wird, werden die Objektvariablen mit `Nothing`initialisiert.</span><span class="sxs-lookup"><span data-stu-id="16c4a-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="16c4a-108">Diejenigen, deren Deklarationen die Initialisierung einschließen, werden auf die Werte, die Sie beim Ausführen der Deklarations Anweisungen angeben, erneut initialisiert.</span><span class="sxs-lookup"><span data-stu-id="16c4a-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>

<span data-ttu-id="16c4a-109">Sie können die Initialisierung in die Deklaration einschließen, indem Sie das [New](../../../../visual-basic/language-reference/operators/new-operator.md) -Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="16c4a-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="16c4a-110">Die folgenden Deklarations Anweisungen deklarieren Objektvariablen `testUri` und `ver` und weisen Ihnen bestimmte Objekte zu.</span><span class="sxs-lookup"><span data-stu-id="16c4a-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="16c4a-111">Jeder verwendet einen der überladenen Konstruktoren der entsprechenden-Klasse, um das Objekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="16c4a-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>

```vb
Dim testUri As New System.Uri("https://www.microsoft.com")
Dim ver As New System.Version(6, 1, 0)
```

## <a name="disassociation"></a><span data-ttu-id="16c4a-112">Aufhebung</span><span class="sxs-lookup"><span data-stu-id="16c4a-112">Disassociation</span></span>

<span data-ttu-id="16c4a-113">Wenn eine Objekt Variable auf `Nothing` festgelegt wird, wird die Zuordnung der Variablen zu einem bestimmten Objekt aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="16c4a-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="16c4a-114">Dadurch wird verhindert, dass das Objekt versehentlich geändert wird, indem die Variable geändert wird.</span><span class="sxs-lookup"><span data-stu-id="16c4a-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="16c4a-115">Außerdem können Sie überprüfen, ob die Objekt Variable auf ein gültiges Objekt verweist, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="16c4a-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>

```vb
If otherObject IsNot Nothing Then
    ' otherObject refers to a valid object, so your code can use it.
End If
```

<span data-ttu-id="16c4a-116">Wenn sich das Objekt, auf das sich Ihre Variable bezieht, in einer anderen Anwendung befindet, kann dieser Test nicht bestimmen, ob die Anwendung beendet wurde oder das Objekt nur für ungültig erklärt hat.</span><span class="sxs-lookup"><span data-stu-id="16c4a-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>

<span data-ttu-id="16c4a-117">Eine Objekt Variable mit dem Wert `Nothing` wird auch als NULL- *Verweis*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="16c4a-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>

## <a name="current-instance"></a><span data-ttu-id="16c4a-118">Aktuelle Instanz</span><span class="sxs-lookup"><span data-stu-id="16c4a-118">Current Instance</span></span>

<span data-ttu-id="16c4a-119">Die *aktuelle Instanz* eines Objekts ist die Instanz, in der der Code gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="16c4a-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="16c4a-120">Da der gesamte Code innerhalb einer Prozedur ausgeführt wird, ist die aktuelle Instanz diejenige, in der die Prozedur aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="16c4a-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>

<span data-ttu-id="16c4a-121">Das `Me`-Schlüsselwort fungiert als Objekt Variable, die auf die aktuelle Instanz verweist.</span><span class="sxs-lookup"><span data-stu-id="16c4a-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="16c4a-122">Wenn eine Prozedur nicht frei [gegeben](../../../../visual-basic/language-reference/modifiers/shared.md)wird, kann Sie das `Me`-Schlüsselwort verwenden, um einen Zeiger auf die aktuelle Instanz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="16c4a-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="16c4a-123">Freigegebene Prozeduren können nicht mit einer bestimmten Instanz einer Klasse verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="16c4a-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>

<span data-ttu-id="16c4a-124">Die Verwendung von `Me` ist besonders nützlich, um die aktuelle Instanz an eine Prozedur in einem anderen Modul zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="16c4a-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="16c4a-125">Angenommen, Sie verfügen über eine Reihe von XML-Dokumenten und möchten allen Standardtext hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="16c4a-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="16c4a-126">Im folgenden Beispiel wird eine Vorgehensweise definiert.</span><span class="sxs-lookup"><span data-stu-id="16c4a-126">The following example defines a procedure to do this.</span></span>

```vb
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)
    XmlDoc.CreateTextNode("This text goes into every XML document.")
End Sub
```

<span data-ttu-id="16c4a-127">Jedes XML-Dokument Objekt könnte dann die Prozedur aufzurufen und die aktuelle Instanz als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="16c4a-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="16c4a-128">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="16c4a-128">The following example demonstrates this.</span></span>

```vb
addStandardText(Me)
```

## <a name="see-also"></a><span data-ttu-id="16c4a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16c4a-129">See also</span></span>

- [<span data-ttu-id="16c4a-130">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="16c4a-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="16c4a-131">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="16c4a-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="16c4a-132">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="16c4a-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="16c4a-133">Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16c4a-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="16c4a-134">Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen</span><span class="sxs-lookup"><span data-stu-id="16c4a-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [<span data-ttu-id="16c4a-135">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="16c4a-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
