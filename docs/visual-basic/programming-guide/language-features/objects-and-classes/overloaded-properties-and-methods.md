---
title: "Überladene Eigenschaften und Methoden (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names, multiple procedures with same
- procedures, mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword, overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0b0040f78fd8e091027e32efae3a0f26c2a08622
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="83ea1-102">Überladene Eigenschaften und Methoden (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83ea1-102">Overloaded Properties and Methods (Visual Basic)</span></span>
<span data-ttu-id="83ea1-103">Überladen ist das Erstellen von mehreren Prozeduren, Instanzkonstruktor oder Eigenschaft in einer Klasse mit dem gleichen Namen, aber unterschiedliche Argumenttypen.</span><span class="sxs-lookup"><span data-stu-id="83ea1-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="83ea1-104">Verwenden der Überladung</span><span class="sxs-lookup"><span data-stu-id="83ea1-104">Overloading Usage</span></span>  
 <span data-ttu-id="83ea1-105">Überladen ist besonders nützlich, wenn das Objektmodell erforderlich macht, dass Sie identische Namen für Prozeduren verwenden, die auf unterschiedliche Datentypen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="83ea1-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="83ea1-106">Angenommen, eine Klasse, die mehrere unterschiedliche Datentypen anzeigen kann verfügen über `Display` Prozeduren, die wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="83ea1-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 <span data-ttu-id="83ea1-107">[!code-vb[VbVbalrOOP&#64;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="83ea1-107">[!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="83ea1-108">Ohne überladen müssten Sie unterschiedliche Namen für jede Prozedur erstellen, obwohl sie das gleiche tun, wie nachfolgend dargestellt:</span><span class="sxs-lookup"><span data-stu-id="83ea1-108">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 <span data-ttu-id="83ea1-109">[!code-vb[VbVbalrOOP&#65;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="83ea1-109">[!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="83ea1-110">Überladen erleichtert es, Eigenschaften oder Methoden verwenden, da sie eine Auswahl von Datentypen enthält, die verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="83ea1-110">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="83ea1-111">Angenommen, die überladene `Display` beschriebene Methode zuvor kann aufgerufen werden mit den folgenden Codezeilen:</span><span class="sxs-lookup"><span data-stu-id="83ea1-111">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 <span data-ttu-id="83ea1-112">[!code-vb[VbVbalrOOP&#66;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="83ea1-112">[!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="83ea1-113">Zur Laufzeit [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Aufrufe, die die richtige Prozedur auf der Grundlage der Datentypen der Parameter Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="83ea1-113">At run time, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="83ea1-114">Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="83ea1-114">Overloading Rules</span></span>  
 <span data-ttu-id="83ea1-115">Erstellen Sie einen überladene Member für eine Klasse durch Hinzufügen von zwei oder mehr Eigenschaften oder Methoden mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="83ea1-115">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="83ea1-116">Mit Ausnahme von überladenen abgeleiteten Membern jeder überladene Member muss unterschiedliche Parameterlisten aufweisen, und die folgenden Elemente nicht als unterscheidendes Merkmal verwendet werden, wenn eine Eigenschaft oder Prozedur überladen:</span><span class="sxs-lookup"><span data-stu-id="83ea1-116">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="83ea1-117">Modifizierer, wie z. B. `ByVal` oder `ByRef`, gilt für einen Member oder Parameter des Members.</span><span class="sxs-lookup"><span data-stu-id="83ea1-117">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="83ea1-118">Namen von Parametern</span><span class="sxs-lookup"><span data-stu-id="83ea1-118">Names of parameters</span></span>  
  
-   <span data-ttu-id="83ea1-119">Rückgabetypen von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="83ea1-119">Return types of procedures</span></span>  
  
 <span data-ttu-id="83ea1-120">Die `Overloads` -Schlüsselwort ist beim Überladen optional, aber wenn eine überladene Member verwendet die `Overloads` -Schlüsselwort, und klicken Sie dann auf alle anderen überladene Member mit demselben Namen müssen auch dieses Schlüsselwort angeben.</span><span class="sxs-lookup"><span data-stu-id="83ea1-120">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="83ea1-121">Abgeleitete Klassen können geerbte Member mit Membern, die über identische Parameter und Parametertypen verfügen genannten überladen *mit Name und Signatur shadowing*.</span><span class="sxs-lookup"><span data-stu-id="83ea1-121">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="83ea1-122">Wenn die `Overloads` -Schlüsselwort wird verwendet, wenn shadowing nach Name und die Signatur, die abgeleitete Klasse die Implementierung des Members anstelle der Implementierung in der Basisklasse verwendet werden, und alle anderen Überladungen für diesen Member für Instanzen der abgeleiteten Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="83ea1-122">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="83ea1-123">Wenn die `Overloads` -Schlüsselwort ausgelassen wird, wenn ein geerbtes Members mit einem Member zu überladen, die über identische Parameter und Parametertypen verfügt, dann heißt das Überladen *shadowing nach Namen*.</span><span class="sxs-lookup"><span data-stu-id="83ea1-123">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="83ea1-124">Ein Shadowing nach dem Namen die geerbte Implementierung eines Elements ersetzt, und die alle anderen Überladungen auf Instanzen von der abgeleiteten Klasse und der Decedents nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="83ea1-124">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="83ea1-125">Die `Overloads` und `Shadows` -Modifizierer können nicht zusammen mit derselben Eigenschaft oder Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="83ea1-125">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="83ea1-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="83ea1-126">Example</span></span>  
 <span data-ttu-id="83ea1-127">Das folgende Beispiel erstellt die überladene Methoden, die entweder akzeptieren ein `String` oder `Decimal` Darstellung eines Währungsbetrag und eine Zeichenfolge mit der entsprechenden Umsatzsteuer zurück.</span><span class="sxs-lookup"><span data-stu-id="83ea1-127">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="83ea1-128">In diesem Beispiel verwenden, um eine überladene Methode erstellen</span><span class="sxs-lookup"><span data-stu-id="83ea1-128">To use this example to create an overloaded method</span></span>  
  
1.  <span data-ttu-id="83ea1-129">Öffnen Sie ein neues Projekt und fügen Sie eine Klasse mit dem Namen `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="83ea1-129">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="83ea1-130">Fügen Sie der `TaxClass`-Klasse folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="83ea1-130">Add the following code to the `TaxClass` class.</span></span>  
  
     <span data-ttu-id="83ea1-131">[!code-vb[VbVbalrOOP&#67;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="83ea1-131">[!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]</span></span>  
  
3.  <span data-ttu-id="83ea1-132">Fügen Sie die folgende Prozedur in das Formular.</span><span class="sxs-lookup"><span data-stu-id="83ea1-132">Add the following procedure to your form.</span></span>  
  
     <span data-ttu-id="83ea1-133">[!code-vb[VbVbalrOOP&#68;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="83ea1-133">[!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]</span></span>  
  
4.  <span data-ttu-id="83ea1-134">Hinzufügen einer Schaltfläche zu Ihrem Formular ein und rufen die `ShowTax` Prozedur aus dem `Button1_Click` -Ereignis der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="83ea1-134">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="83ea1-135">Führen Sie das Projekt, und klicken Sie auf die Schaltfläche auf dem Formular so testen Sie die überladenen `ShowTax` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="83ea1-135">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="83ea1-136">Zur Laufzeit wählt der Compiler den geeignete überladene Funktion, die die Parametern entspricht.</span><span class="sxs-lookup"><span data-stu-id="83ea1-136">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="83ea1-137">Wenn Sie auf die Schaltfläche klicken, die überladene Methode zuerst aufgerufen mit einem `Price` -Parameter, der eine Zeichenfolge ist und die Meldung "Preis ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="83ea1-137">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="83ea1-138">Steuer ist $5,12" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="83ea1-138">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="83ea1-139">`TaxAmount`wird aufgerufen, mit einem `Decimal` Wert erneut und der Meldung, "Preis ist eine Dezimalzahl.</span><span class="sxs-lookup"><span data-stu-id="83ea1-139">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="83ea1-140">Steuer ist $5,12" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="83ea1-140">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ea1-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83ea1-141">See Also</span></span>  
 <span data-ttu-id="83ea1-142">[Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="83ea1-142">[Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="83ea1-143"> [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md) </span><span class="sxs-lookup"><span data-stu-id="83ea1-143"> [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md) </span></span>  
<span data-ttu-id="83ea1-144"> [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="83ea1-144"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="83ea1-145"> [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) </span><span class="sxs-lookup"><span data-stu-id="83ea1-145"> [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) </span></span>  
<span data-ttu-id="83ea1-146"> [Schatten](../../../../visual-basic/language-reference/modifiers/shadows.md) </span><span class="sxs-lookup"><span data-stu-id="83ea1-146"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) </span></span>  
<span data-ttu-id="83ea1-147"> [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) </span><span class="sxs-lookup"><span data-stu-id="83ea1-147"> [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) </span></span>  
<span data-ttu-id="83ea1-148"> [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) </span><span class="sxs-lookup"><span data-stu-id="83ea1-148"> [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) </span></span>  
<span data-ttu-id="83ea1-149"> [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md) </span><span class="sxs-lookup"><span data-stu-id="83ea1-149"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) </span></span>  
<span data-ttu-id="83ea1-150"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)</span><span class="sxs-lookup"><span data-stu-id="83ea1-150"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)</span></span>
