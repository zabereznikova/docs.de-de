---
title: Überladene Eigenschaften und Methoden
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
ms.openlocfilehash: 1672f12773ece012c580253b6dafbf9d0ac8f07c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389151"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="60da5-102">Überladene Eigenschaften und Methoden (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60da5-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="60da5-103">Überladen ist die Erstellung von mehr als einer Prozedur, einem Instanzkonstruktor oder einer Eigenschaft in einer Klasse mit demselben Namen, aber unterschiedlichen Argument Typen.</span><span class="sxs-lookup"><span data-stu-id="60da5-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="60da5-104">Überladen der Verwendung</span><span class="sxs-lookup"><span data-stu-id="60da5-104">Overloading usage</span></span>

<span data-ttu-id="60da5-105">Das überladen ist besonders nützlich, wenn das Objektmodell vorschreibt, dass Sie identische Namen für Prozeduren verwenden, die auf unterschiedliche Datentypen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="60da5-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="60da5-106">Beispielsweise könnte eine Klasse, die mehrere unterschiedliche Datentypen anzeigen kann, über `Display` Prozeduren verfügen, die wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="60da5-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="60da5-107">Ohne überladen müssen Sie für jede Prozedur eindeutige Namen erstellen, auch wenn Sie das gleiche tun, wie im folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="60da5-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="60da5-108">Das überladen vereinfacht die Verwendung von Eigenschaften oder Methoden, da es eine Auswahl von Datentypen ermöglicht, die verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="60da5-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="60da5-109">Beispielsweise kann die zuvor beschriebene überladene `Display` Methode mit einer der folgenden Codezeilen aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="60da5-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="60da5-110">Zur Laufzeit ruft Visual Basic die richtige Prozedur auf Grundlage der Datentypen der Parameter auf, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="60da5-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="60da5-111">Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="60da5-111">Overloading rules</span></span>

 <span data-ttu-id="60da5-112">Sie erstellen ein überladenes Element für eine Klasse, indem Sie zwei oder mehr Eigenschaften oder Methoden mit demselben Namen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="60da5-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="60da5-113">Mit Ausnahme überladener abgeleiteter Member muss jedes überladene Element über unterschiedliche Parameterlisten verfügen, und die folgenden Elemente können nicht als differenzierende Funktion verwendet werden, wenn eine Eigenschaft oder Prozedur überladen wird:</span><span class="sxs-lookup"><span data-stu-id="60da5-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="60da5-114">Modifiziererer, z `ByVal` . b. oder `ByRef` , die für einen Member gelten, oder Parameter des Members.</span><span class="sxs-lookup"><span data-stu-id="60da5-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="60da5-115">Parameternamen</span><span class="sxs-lookup"><span data-stu-id="60da5-115">Names of parameters</span></span>

- <span data-ttu-id="60da5-116">Rückgabe Typen von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="60da5-116">Return types of procedures</span></span>

<span data-ttu-id="60da5-117">Das `Overloads` Schlüsselwort ist beim Überladen optional. Wenn jedoch ein überladenes Element das `Overloads` Schlüsselwort verwendet, müssen auch alle anderen überladenen Member mit demselben Namen dieses Schlüsselwort angeben.</span><span class="sxs-lookup"><span data-stu-id="60da5-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="60da5-118">Abgeleitete Klassen können geerbte Member mit Membern mit identischen Parametern und Parametertypen überladen. Dies ist ein Prozess, *der als shadowingby Name und Signatur*bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="60da5-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="60da5-119">Wenn das `Overloads` Schlüsselwort beim shadodown nach Name und Signatur verwendet wird, wird die Implementierung des Members der abgeleiteten Klasse anstelle der Implementierung in der Basisklasse verwendet, und alle anderen über Ladungen für diesen Member sind für Instanzen der abgeleiteten Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="60da5-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="60da5-120">Wenn das- `Overloads` Schlüsselwort beim Überladen eines geerbten Members mit einem Member mit identischen Parametern und Parametertypen weggelassen wird, wird das überladen als *shadowingby Name*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="60da5-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="60da5-121">Shadowingby Name ersetzt die geerbte Implementierung eines Members und macht alle anderen über Ladungen für Instanzen der abgeleiteten Klasse und deren Elemente nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="60da5-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="60da5-122">Die `Overloads` `Shadows` modifiziererer und können nicht gleichzeitig mit der gleichen Eigenschaft oder Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60da5-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="60da5-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60da5-123">Example</span></span>

<span data-ttu-id="60da5-124">Im folgenden Beispiel werden überladene Methoden erstellt, die entweder eine- `String` oder `Decimal` -Darstellung eines Dollarbetrags akzeptieren und eine Zeichenfolge zurückgeben, die die Verkaufssteuer enthält.</span><span class="sxs-lookup"><span data-stu-id="60da5-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="60da5-125">So verwenden Sie dieses Beispiel zum Erstellen einer überladenen Methode</span><span class="sxs-lookup"><span data-stu-id="60da5-125">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="60da5-126">Öffnen Sie ein neues Projekt, und fügen Sie eine Klasse namens hinzu `TaxClass` .</span><span class="sxs-lookup"><span data-stu-id="60da5-126">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="60da5-127">Fügen Sie der `TaxClass` -Klasse den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="60da5-127">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="60da5-128">Fügen Sie dem Formular die folgende Prozedur hinzu.</span><span class="sxs-lookup"><span data-stu-id="60da5-128">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="60da5-129">Fügen Sie dem Formular eine Schaltfläche hinzu, und nennen Sie die `ShowTax` Prozedur aus dem- `Button1_Click` Ereignis der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="60da5-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="60da5-130">Führen Sie das Projekt aus, und klicken Sie auf die Schaltfläche auf dem Formular, um die überladene `ShowTax` Prozedur</span><span class="sxs-lookup"><span data-stu-id="60da5-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="60da5-131">Zur Laufzeit wählt der Compiler die geeignete überladene Funktion aus, die den verwendeten Parametern entspricht.</span><span class="sxs-lookup"><span data-stu-id="60da5-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="60da5-132">Wenn Sie auf die Schaltfläche klicken, wird die überladene Methode zuerst mit einem Parameter aufgerufen, bei dem `Price` es sich um eine Zeichenfolge handelt, und die Meldung "Price ist eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="60da5-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="60da5-133">Steuern ist $5,12 "wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60da5-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="60da5-134">`TaxAmount`wird mit einem `Decimal` Wert beim zweiten Mal und in der Meldung "price is a Decimal" aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="60da5-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="60da5-135">Steuern ist $5,12 "wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60da5-135">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="60da5-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60da5-136">See also</span></span>

- [<span data-ttu-id="60da5-137">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="60da5-137">Objects and Classes</span></span>](index.md)
- [<span data-ttu-id="60da5-138">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60da5-138">Shadowing in Visual Basic</span></span>](../declared-elements/shadowing.md)
- [<span data-ttu-id="60da5-139">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="60da5-139">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="60da5-140">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="60da5-140">Inheritance Basics</span></span>](inheritance-basics.md)
- [<span data-ttu-id="60da5-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="60da5-141">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="60da5-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="60da5-142">ByVal</span></span>](../../../language-reference/modifiers/byval.md)
- [<span data-ttu-id="60da5-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="60da5-143">ByRef</span></span>](../../../language-reference/modifiers/byref.md)
- [<span data-ttu-id="60da5-144">Overloads</span><span class="sxs-lookup"><span data-stu-id="60da5-144">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="60da5-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="60da5-145">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
