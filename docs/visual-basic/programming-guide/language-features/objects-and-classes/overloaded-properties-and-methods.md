---
title: Überladene Eigenschaften und Methoden (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: 8d7341370d9770d2e57f786ac7c68277e66a9bbd
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57677395"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="2aa09-102">Überladene Eigenschaften und Methoden (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2aa09-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="2aa09-103">Überladen ist die Erstellung von mehr als eine Prozedur, Instanzenkonstruktor oder Eigenschaft in einer Klasse mit dem gleichen Namen, aber unterschiedliche Argumenttypen.</span><span class="sxs-lookup"><span data-stu-id="2aa09-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="2aa09-104">Verwenden der Überladung</span><span class="sxs-lookup"><span data-stu-id="2aa09-104">Overloading usage</span></span>

<span data-ttu-id="2aa09-105">Überladen ist besonders nützlich, wenn Ihr Objektmodell vorgegeben, die Verwendung identischer Namen für Prozeduren, die für unterschiedliche Datentypen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2aa09-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="2aa09-106">Z. B. eine Klasse, die mehrere unterschiedliche Datentypen anzeigen, können möglicherweise `Display` Prozeduren, die wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="2aa09-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="2aa09-107">Ohne überladen zulässt müssten Sie unterschiedliche Namen für jede Prozedur zu erstellen, auch wenn sie das tun. wie im folgenden gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2aa09-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="2aa09-108">Überladen von erleichtert es, Eigenschaften oder Methoden zu verwenden, da sie eine Auswahl von Datentypen enthält, die verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2aa09-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="2aa09-109">Z. B. die überladene `Display` Methode erläutert zuvor kann aufgerufen werden mit den folgenden Codezeilen:</span><span class="sxs-lookup"><span data-stu-id="2aa09-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="2aa09-110">Zur Laufzeit ruft die Visual Basic die richtige Prozedur, die auf Grundlage der Datentypen der Parameter, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="2aa09-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="2aa09-111">Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="2aa09-111">Overloading rules</span></span>

 <span data-ttu-id="2aa09-112">Sie erstellen einen überladenen Member für eine Klasse, durch das Hinzufügen von zwei oder mehr Eigenschaften oder Methoden mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="2aa09-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="2aa09-113">Mit Ausnahme von überladenen Membern abgeleiteten jeder überladene Member müssen die unterschiedlichen Parameterlisten, und die folgenden Elemente können nicht als unterscheidende Merkmal verwendet werden, wenn eine Eigenschaft oder Prozedur zu überladen:</span><span class="sxs-lookup"><span data-stu-id="2aa09-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="2aa09-114">Modifizierer, z. B. `ByVal` oder `ByRef`, gilt für einen Member oder Parameter des Members.</span><span class="sxs-lookup"><span data-stu-id="2aa09-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="2aa09-115">Namen von Parametern</span><span class="sxs-lookup"><span data-stu-id="2aa09-115">Names of parameters</span></span>

- <span data-ttu-id="2aa09-116">Rückgabetypen von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="2aa09-116">Return types of procedures</span></span>

<span data-ttu-id="2aa09-117">Die `Overloads` Schlüsselwort ist optional, beim Überladen, aber ggf. überladene Member verwendet die `Overloads` -Schlüsselwort, und klicken Sie dann auf alle anderen überladene Member mit demselben Namen müssen auch dieses Schlüsselwort angeben.</span><span class="sxs-lookup"><span data-stu-id="2aa09-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="2aa09-118">Abgeleitete Klassen können geerbte Member mit Member mit identischen Parametern und die Parametertypen, eines Prozesses Namens überladen *shadowing nach Namen und derselben Signatur*.</span><span class="sxs-lookup"><span data-stu-id="2aa09-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="2aa09-119">Wenn die `Overloads` -Schlüsselwort wird verwendet, wenn shadowing nach Name und Signatur, Implementierung des Members der abgeleiteten Klasse anstelle der Implementierung in der Basisklasse verwendet werden aus, und alle anderen Überladungen für dieses Element Instanzen von werden der abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="2aa09-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="2aa09-120">Wenn die `Overloads` -Schlüsselwort ausgelassen wird, beim Überladen von eines geerbten Members mit einem Member, die über identische Parameter und die Parametertypen verfügt, und klicken Sie dann die Überladung wird aufgerufen, *nach Namen shadowing*.</span><span class="sxs-lookup"><span data-stu-id="2aa09-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="2aa09-121">Nach dem Namen Shadowing die geerbte Implementierung eines Elements ersetzt, und es allen anderen Überladungen für Instanzen von der abgeleiteten Klasse und die Decedents nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2aa09-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="2aa09-122">Die `Overloads` und `Shadows` -Modifizierer können nicht zusammen mit der gleichen Eigenschaft oder Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2aa09-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="2aa09-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2aa09-123">Example</span></span>

<span data-ttu-id="2aa09-124">Das folgende Beispiel erstellt überladene Methoden, die entweder akzeptieren einen `String` oder `Decimal` Darstellung eines Dollarbetrag und der Rückgabewert eine Zeichenfolge, die die Mehrwertsteuer enthält.</span><span class="sxs-lookup"><span data-stu-id="2aa09-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="2aa09-125">In diesem Beispiel verwenden, um eine überladene Methode erstellen</span><span class="sxs-lookup"><span data-stu-id="2aa09-125">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="2aa09-126">Öffnen Sie ein neues Projekt, und fügen Sie eine Klasse, die mit dem Namen `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="2aa09-126">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="2aa09-127">Fügen Sie der `TaxClass` -Klasse folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="2aa09-127">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="2aa09-128">Fügen Sie das folgende Verfahren zum Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="2aa09-128">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="2aa09-129">Fügen Sie eine Schaltfläche, um Ihr Formular, und rufen die `ShowTax` Prozedur aus der `Button1_Click` -Ereignis der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="2aa09-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="2aa09-130">Führen Sie das Projekt, und klicken Sie auf dem Formular so testen Sie die überladene `ShowTax` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="2aa09-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="2aa09-131">Zur Laufzeit wählt der Compiler die entsprechende überladene Funktion, die den verwendeten Parametern übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2aa09-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="2aa09-132">Wenn Sie die Schaltfläche klicken, die überladene Methode zuerst aufgerufen mit einem `Price` -Parameter, ist eine Zeichenfolge und die Meldung "der Preis ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2aa09-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="2aa09-133">Steuer ist $5,12" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2aa09-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="2aa09-134">`TaxAmount` wird aufgerufen, mit einem `Decimal` Wert der zweiten Ausführung und der Meldung, "Preis ist eine Dezimalzahl.</span><span class="sxs-lookup"><span data-stu-id="2aa09-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="2aa09-135">Steuer ist $5,12" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2aa09-135">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="2aa09-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2aa09-136">See also</span></span>

- [<span data-ttu-id="2aa09-137">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="2aa09-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="2aa09-138">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2aa09-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="2aa09-139">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2aa09-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="2aa09-140">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="2aa09-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="2aa09-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="2aa09-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="2aa09-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="2aa09-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)
- [<span data-ttu-id="2aa09-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="2aa09-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)
- [<span data-ttu-id="2aa09-144">Overloads</span><span class="sxs-lookup"><span data-stu-id="2aa09-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="2aa09-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="2aa09-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
