---
title: Zuweisen von Objektvariablen (Visual Basic)
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
ms.openlocfilehash: f20a03c4d9a0e33203629ae066686f4c9f25c105
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656057"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="952c8-102">Zuweisen von Objektvariablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="952c8-102">Object Variable Assignment (Visual Basic)</span></span>
<span data-ttu-id="952c8-103">Sie verwenden eine normale zuweisungsanweisung Objektvariable ein Objekt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="952c8-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="952c8-104">Sie können ein Objektausdrücke zuweisen oder die [nichts](../../../../visual-basic/language-reference/nothing.md) -Schlüsselwort, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="952c8-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 <span data-ttu-id="952c8-105">`Nothing` bedeutet, es wurde kein Objekt, das der Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="952c8-105">`Nothing` means there is no object currently assigned to the variable.</span></span>  
  
## <a name="initialization"></a><span data-ttu-id="952c8-106">Initialisierung</span><span class="sxs-lookup"><span data-stu-id="952c8-106">Initialization</span></span>  
 <span data-ttu-id="952c8-107">Wenn Ihr Code beginnt die Ausführung, Ihr Objekts Variablen werden initialisiert, um `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="952c8-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="952c8-108">Diejenigen, deren Deklarationen Initialisierung enthalten, sind, die Werte erneut initialisiert, die Sie angeben, wenn die deklarationsanweisungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="952c8-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>  
  
 <span data-ttu-id="952c8-109">Sie können die Initialisierung in der Deklaration einschließen, mit der [neu](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="952c8-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="952c8-110">Die folgende deklarationsanweisungen deklarieren Objektvariablen `testUri` und `ver` und bestimmte Objekte zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="952c8-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="952c8-111">Jede verwendet eine der überladenen Konstruktoren der entsprechenden Klasse zum Initialisieren des Objekts.</span><span class="sxs-lookup"><span data-stu-id="952c8-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a><span data-ttu-id="952c8-112">Disassocation</span><span class="sxs-lookup"><span data-stu-id="952c8-112">Disassociation</span></span>  
 <span data-ttu-id="952c8-113">Festlegen einer Objektvariablen auf `Nothing` reagiert nicht mehr, die Zuordnung der Variablen mit bestimmten Objekts.</span><span class="sxs-lookup"><span data-stu-id="952c8-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="952c8-114">Dies verhindert, dass Sie fälschlicherweise das Objekt durch Ändern der Variablen ändert.</span><span class="sxs-lookup"><span data-stu-id="952c8-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="952c8-115">Zudem können Sie zum Überprüfen, ob die Objektvariable auf ein gültiges Objekt, wie im folgenden Beispiel gezeigt verweist.</span><span class="sxs-lookup"><span data-stu-id="952c8-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 <span data-ttu-id="952c8-116">Wenn das Objekt, auf dem die Variable verweist in einer anderen Anwendung, kann nicht diesen Test bestimmen, ob die Anwendung beendet wurde, oder das Objekt nur für ungültig zu erklären.</span><span class="sxs-lookup"><span data-stu-id="952c8-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>  
  
 <span data-ttu-id="952c8-117">Ein Object-Variablen mit einem Wert von `Nothing` steht eine *null-Verweis*.</span><span class="sxs-lookup"><span data-stu-id="952c8-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>  
  
## <a name="current-instance"></a><span data-ttu-id="952c8-118">Aktuelle Instanz</span><span class="sxs-lookup"><span data-stu-id="952c8-118">Current Instance</span></span>  
 <span data-ttu-id="952c8-119">Die *aktuelle Instanz* eines Objekts wird in dem der Code derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="952c8-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="952c8-120">Da der gesamte Code innerhalb einer Prozedur ausgeführt wird, wird die aktuelle Instanz in der die Prozedur aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="952c8-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>  
  
 <span data-ttu-id="952c8-121">Die `Me` -Schlüsselwort fungiert als eine Objektvariable verweist auf die aktuelle Instanz.</span><span class="sxs-lookup"><span data-stu-id="952c8-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="952c8-122">Eine Prozedur ist nicht [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), kann die `Me` Schlüsselwort, um einen Zeiger auf die aktuelle Instanz.</span><span class="sxs-lookup"><span data-stu-id="952c8-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="952c8-123">Freigegebene Prozeduren können nicht mit einer bestimmten Instanz einer Klasse zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="952c8-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>  
  
 <span data-ttu-id="952c8-124">Mithilfe von `Me` ist besonders nützlich für die aktuelle Instanz an eine Prozedur in einem anderen Modul übergeben.</span><span class="sxs-lookup"><span data-stu-id="952c8-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="952c8-125">Nehmen wir beispielsweise an, Sie verfügen über eine Reihe von XML-Dokumenten und einige standard-Text hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="952c8-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="952c8-126">Das folgende Beispiel definiert eine Prozedur zu diesem Zweck.</span><span class="sxs-lookup"><span data-stu-id="952c8-126">The following example defines a procedure to do this.</span></span>  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 <span data-ttu-id="952c8-127">Jedes XML-Dokumentobjekt kann dann rufen Sie die Prozedur und die aktuelle Instanz als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="952c8-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="952c8-128">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="952c8-128">The following example demonstrates this.</span></span>  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a><span data-ttu-id="952c8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="952c8-129">See Also</span></span>  
 [<span data-ttu-id="952c8-130">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="952c8-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="952c8-131">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="952c8-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="952c8-132">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="952c8-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="952c8-133">Vorgehensweise: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="952c8-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [<span data-ttu-id="952c8-134">Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen</span><span class="sxs-lookup"><span data-stu-id="952c8-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [<span data-ttu-id="952c8-135">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="952c8-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
