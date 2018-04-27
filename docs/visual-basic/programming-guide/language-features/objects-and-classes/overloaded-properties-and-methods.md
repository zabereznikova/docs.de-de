---
title: Überladene Eigenschaften und Methoden (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 96d5ef2462f5312baa5269865977596035a254d5
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="1827e-102">Überladene Eigenschaften und Methoden (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1827e-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="1827e-103">Überladen ist die Erstellung von mehr als eine Prozedur, Instanzkonstruktor oder Eigenschaft in einer Klasse mit dem gleichen Namen, aber unterschiedliche Argumenttypen.</span><span class="sxs-lookup"><span data-stu-id="1827e-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="1827e-104">Überladen Verbrauch</span><span class="sxs-lookup"><span data-stu-id="1827e-104">Overloading usage</span></span>

 <span data-ttu-id="1827e-105">Überladen ist besonders nützlich, wenn Ihr Objektmodell vorgegeben, die Verwendung identischer Namen für Prozeduren, die für unterschiedliche Datentypen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1827e-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="1827e-106">Z. B. eine Klasse, die mehrere unterschiedliche Datentypen anzeigen sollen, kann möglicherweise `Display` Prozeduren, die wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1827e-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 [!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]
  
 <span data-ttu-id="1827e-107">Ohne überladen müssten Sie unterschiedliche Namen für jede Prozedur erstellen, auch wenn sie dasselbe, führen Sie als Nächstes dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1827e-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 [!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]
  
 <span data-ttu-id="1827e-108">Überladen von erleichtert es, Eigenschaften oder Methoden verwendet werden, da es sich um eine Auswahl von Datentypen bereitstellt, die verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1827e-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="1827e-109">Z. B. die überladene `Display` erläutert zuvor kann aufgerufen werden mit den folgenden Codezeilen:</span><span class="sxs-lookup"><span data-stu-id="1827e-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 [!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]
  
 <span data-ttu-id="1827e-110">Zur Laufzeit ruft Visual Basic das korrekte Verfahren basierend auf den Datentypen der Parameter, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="1827e-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="1827e-111">Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="1827e-111">Overloading rules</span></span>

 <span data-ttu-id="1827e-112">Sie erstellen ein überladenen Members für eine Klasse, durch Hinzufügen von zwei oder mehr Eigenschaften oder Methoden mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="1827e-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="1827e-113">Mit Ausnahme von überladenen Membern abgeleiteten jeder überladene Member muss unterschiedlichen Parameterlisten aufweisen, und die folgenden Elemente können nicht als Unterscheidungsmerkmal Feature beim Überladen einer Eigenschaft oder Prozedur verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="1827e-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="1827e-114">Modifizierer, wie z. B. `ByVal` oder `ByRef`, gilt für einen Member oder Parameter des Members.</span><span class="sxs-lookup"><span data-stu-id="1827e-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="1827e-115">Namen von Parametern</span><span class="sxs-lookup"><span data-stu-id="1827e-115">Names of parameters</span></span>  
  
-   <span data-ttu-id="1827e-116">Rückgabetypen von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1827e-116">Return types of procedures</span></span>  
  
 <span data-ttu-id="1827e-117">Die `Overloads` Schlüsselwort ist optional, beim Überladen, aber wenn eine überladene Member verwendet die `Overloads` -Schlüsselwort, und klicken Sie dann auf alle anderen überladene Member mit demselben Namen müssen auch dieses Schlüsselwort angeben.</span><span class="sxs-lookup"><span data-stu-id="1827e-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="1827e-118">Abgeleitete Klassen können geerbte Member mit Member mit identischen Parametern und die Parametertypen, genannten überladen *shadowing durch den Namen und derselben Signatur*.</span><span class="sxs-lookup"><span data-stu-id="1827e-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="1827e-119">Wenn die `Overloads` Schlüsselwort wird verwendet, wenn shadowing nach Namen und derselben Signatur, die abgeleitete Klasse die Implementierung des Elements anstelle der Implementierung in der Basisklasse verwendet werden, und alle anderen Überladungen für dieses Element ist verfügbar auf Instanzen von der abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="1827e-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="1827e-120">Wenn die `Overloads` -Schlüsselwort ausgelassen wird, wenn einen geerbten Member mit einem Member zu überladen, die identische Parameter und Parametertypen aufweist, und klicken Sie dann das überladen wird aufgerufen, *namentlich shadowing*.</span><span class="sxs-lookup"><span data-stu-id="1827e-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="1827e-121">Shadowing anhand des Namens die geerbte Implementierung eines Elements ersetzt, und es macht alle anderen Überladungen auf Instanzen von der abgeleiteten Klasse und ihre Decedents nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1827e-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="1827e-122">Die `Overloads` und `Shadows` Modifizierer können nicht zusammen mit dem gleichen Eigenschaft oder Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1827e-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="1827e-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1827e-123">Example</span></span>

 <span data-ttu-id="1827e-124">Das folgende Beispiel erstellt die überladene Methoden, die entweder akzeptieren ein `String` oder `Decimal` Darstellung ein Währungsbetrag und der Rückgabewert eine Zeichenfolge, die die Mehrwertsteuer enthält.</span><span class="sxs-lookup"><span data-stu-id="1827e-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="1827e-125">In diesem Beispiel verwenden, um eine überladene Methode erstellen</span><span class="sxs-lookup"><span data-stu-id="1827e-125">To use this example to create an overloaded method</span></span>
  
1.  <span data-ttu-id="1827e-126">Öffnen Sie ein neues Projekt und fügen Sie eine Klasse mit dem Namen `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="1827e-126">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="1827e-127">Fügen Sie der `TaxClass`-Klasse folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="1827e-127">Add the following code to the `TaxClass` class.</span></span>  
  
     [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]
  
3.  <span data-ttu-id="1827e-128">Fügen Sie das folgende Verfahren zum Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="1827e-128">Add the following procedure to your form.</span></span>  
  
     [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]
  
4.  <span data-ttu-id="1827e-129">Fügen Sie eine Schaltfläche auf Ihrem Formular, und rufen die `ShowTax` Prozedur aus dem `Button1_Click` -Ereignis der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="1827e-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="1827e-130">Führen Sie das Projekt, und klicken Sie auf die Schaltfläche auf dem Formular so testen Sie die überladene `ShowTax` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="1827e-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="1827e-131">Zur Laufzeit wählt der Compiler die entsprechenden überladene Funktion, die den verwendeten Parametern übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="1827e-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="1827e-132">Wenn Sie die Schaltfläche klicken, die überladene Methode wird aufgerufen zunächst mit einer `Price` -Parameter, ist eine Zeichenfolge und die Meldung "Preis ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1827e-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="1827e-133">Tax ist $5,12" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1827e-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="1827e-134">`TaxAmount` wird aufgerufen, mit einem `Decimal` Wert ein zweites Mal und der Meldung, die "Preis ist eine Dezimalzahl.</span><span class="sxs-lookup"><span data-stu-id="1827e-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="1827e-135">Tax ist $5,12" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1827e-135">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1827e-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1827e-136">See also</span></span>

 [<span data-ttu-id="1827e-137">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="1827e-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="1827e-138">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1827e-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="1827e-139">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1827e-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="1827e-140">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="1827e-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="1827e-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="1827e-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="1827e-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="1827e-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [<span data-ttu-id="1827e-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="1827e-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [<span data-ttu-id="1827e-144">Overloads</span><span class="sxs-lookup"><span data-stu-id="1827e-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="1827e-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="1827e-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
