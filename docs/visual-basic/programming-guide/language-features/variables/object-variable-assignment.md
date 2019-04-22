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
ms.openlocfilehash: dff1b9bb9e87f827663786cac3f33531db41b2c1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840275"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="aa6fe-102">Zuweisen von Objektvariablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa6fe-102">Object Variable Assignment (Visual Basic)</span></span>
<span data-ttu-id="aa6fe-103">Sie verwenden eine normale Anweisung ein Objekt einer Objektvariablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="aa6fe-104">Sie können den Objektausdruck ein zuweisen oder die ["Nothing"](../../../../visual-basic/language-reference/nothing.md) -Schlüsselwort, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 <span data-ttu-id="aa6fe-105">`Nothing` bedeutet, dass es kein Objekt, das derzeit auf die Variable zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-105">`Nothing` means there is no object currently assigned to the variable.</span></span>  
  
## <a name="initialization"></a><span data-ttu-id="aa6fe-106">Initialisierung</span><span class="sxs-lookup"><span data-stu-id="aa6fe-106">Initialization</span></span>  
 <span data-ttu-id="aa6fe-107">Wenn Ihr Code beginnt, ausgeführt wird, wird das Objekt, das Variablen werden initialisiert, um `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="aa6fe-108">Diejenigen, deren Deklarationen Initialisierung enthalten, sind, die Werte erneut initialisiert, die Sie angeben, wenn die deklarationsanweisungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>  
  
 <span data-ttu-id="aa6fe-109">Sie können die Initialisierung in der Deklaration einschließen, mithilfe der [neu](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="aa6fe-110">Die folgende deklarationsanweisungen deklarieren Sie Objektvariablen `testUri` und `ver` und Ihnen bestimmte Objekte zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="aa6fe-111">Jede verwendet eine der überladenen Konstruktoren der entsprechenden Klasse zum Initialisieren des Objekts.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>  
  
```  
Dim testUri As New System.Uri("https://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a><span data-ttu-id="aa6fe-112">Durch das Aufheben</span><span class="sxs-lookup"><span data-stu-id="aa6fe-112">Disassociation</span></span>  
 <span data-ttu-id="aa6fe-113">Festlegen einer Objektvariablen auf `Nothing` beendet die Zuordnung der Variablen zu einem bestimmten Objekt.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="aa6fe-114">Dies verhindert, dass Sie fälschlicherweise das Objekt durch Ändern der Variablen ändert.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="aa6fe-115">Außerdem können Sie zum Überprüfen, ob die Objektvariable auf ein gültiges Objekt, wie im folgenden Beispiel gezeigt zeigt.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 <span data-ttu-id="aa6fe-116">Wenn das Objekt, auf die, dem die Variable verweist, in einer anderen Anwendung ist, kann nicht diesen Test bestimmen, ob die Anwendung beendet wurde, oder das Objekt nur für ungültig zu erklären.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>  
  
 <span data-ttu-id="aa6fe-117">Eine Objektvariable mit einem Wert von `Nothing` steht für eine *null-Verweis*.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>  
  
## <a name="current-instance"></a><span data-ttu-id="aa6fe-118">Aktuelle Instanz</span><span class="sxs-lookup"><span data-stu-id="aa6fe-118">Current Instance</span></span>  
 <span data-ttu-id="aa6fe-119">Die *kurveninstanz* eines Objekts wird in der der Code derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="aa6fe-120">Da der gesamte Code innerhalb einer Prozedur ausgeführt wird, wird die aktuelle Instanz in dem die Prozedur aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>  
  
 <span data-ttu-id="aa6fe-121">Die `Me` -Schlüsselwort dient als eine Objektvariable verweist auf die aktuelle Instanz.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="aa6fe-122">Eine Prozedur ist nicht [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), kann die `Me` Schlüsselwort, um einen Zeiger auf die aktuelle Instanz abzurufen.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="aa6fe-123">Freigegebene Prozeduren können nicht mit einer bestimmten Instanz einer Klasse zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>  
  
 <span data-ttu-id="aa6fe-124">Mithilfe von `Me` ist besonders nützlich für die aktuelle Instanz an eine Prozedur in einem anderen Modul übergeben.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="aa6fe-125">Nehmen wir beispielsweise an, Sie verfügen über eine Anzahl von XML-Dokumenten und alle dieser standard Text hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="aa6fe-126">Das folgende Beispiel definiert eine Prozedur zu diesem Zweck.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-126">The following example defines a procedure to do this.</span></span>  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 <span data-ttu-id="aa6fe-127">Jedes XML-Dokument-Objekt kann dann rufen Sie die Prozedur und die aktuelle Instanz als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="aa6fe-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="aa6fe-128">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="aa6fe-128">The following example demonstrates this.</span></span>  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa6fe-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa6fe-129">See also</span></span>

- [<span data-ttu-id="aa6fe-130">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="aa6fe-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="aa6fe-131">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="aa6fe-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="aa6fe-132">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="aa6fe-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="aa6fe-133">Vorgehensweise: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aa6fe-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="aa6fe-134">Vorgehensweise: Einer Objektvariablen verweist nicht auf eine beliebige Instanz</span><span class="sxs-lookup"><span data-stu-id="aa6fe-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [<span data-ttu-id="aa6fe-135">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="aa6fe-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
