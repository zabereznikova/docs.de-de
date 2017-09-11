---
title: Grundlagen der Vererbung (Visual Basic) | Microsoft-Dokumentation
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
- derived classes, inheritance
- MyClass keyword, using
- MyBase keyword, using
- Inherits statement, inheritance
- overriding, Overridable keyword
- MustInherit keyword, using
- Overrides keyword, using
- inheritance
- MustInherit classes
- MustOverride keyword, using
- classes [Visual Basic], derived
- NotInheritable keyword, using
- base classes, extending properties and methods
- NotOverridable keyword, using
- base classes, inheritance
- abstract classes, inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: 23
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
ms.sourcegitcommit: 4892ed6dcfb3843bd6cb2de2d3e032bfeb1efdf9
ms.openlocfilehash: 43b6505634b12f7f8353866e938151f1e00fb073
ms.contentlocale: de-de
ms.lasthandoff: 05/16/2017

---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="ef771-102">Grundlagen der Vererbung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef771-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="ef771-103">Die `Inherits` -Anweisung verwendet, um eine neue Klasse namens deklarieren eine *abgeleitete Klasse*, basierend auf einer vorhandenen Klasse, eine *Basisklasse*.</span><span class="sxs-lookup"><span data-stu-id="ef771-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="ef771-104">Abgeleitete Klassen erben und erweitern können, die Eigenschaften, Methoden, Ereignisse, Felder und Konstanten, die in der Basisklasse definiert.</span><span class="sxs-lookup"><span data-stu-id="ef771-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="ef771-105">Im folgenden Abschnitt werden einige der Regeln für die Vererbung, und die Parameter auf, die Sie verwenden können, so ändern Sie die Möglichkeit Klassen erben oder geerbt werden:</span><span class="sxs-lookup"><span data-stu-id="ef771-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
-   <span data-ttu-id="ef771-106">Standardmäßig sind alle Klassen vererbt, es sei denn, mit dem `NotInheritable` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="ef771-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="ef771-107">Klassen können von anderen Klassen in Ihrem Projekt oder von Klassen in anderen Assemblys, die das Projekt verweist auf erben.</span><span class="sxs-lookup"><span data-stu-id="ef771-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
-   <span data-ttu-id="ef771-108">Im Gegensatz zu den Sprachen, die mehrere Vererbungen zu ermöglichen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] können nur einfache Vererbung in Klassen, abgeleitete Klassen können nur eine Basisklasse, also aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ef771-108">Unlike languages that allow multiple inheritance, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="ef771-109">Mehrfache Vererbung in Klassen nicht zulässig ist, können Klassen mehrere Schnittstellen implementieren, die effektiv desselben erreichen können.</span><span class="sxs-lookup"><span data-stu-id="ef771-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
-   <span data-ttu-id="ef771-110">Um zu verhindern, dass eingeschränkte Elemente in einer Basisklasse verfügbar machen, muss der Zugriffstyp einer abgeleiteten Klasse restriktiver als die Basisklasse oder gleich sein.</span><span class="sxs-lookup"><span data-stu-id="ef771-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="ef771-111">Z. B. eine `Public` Klasse erben kann kein `Friend` oder ein `Private` -Klasse, und ein `Friend` Klasse kann nicht geerbt eine `Private` Klasse.</span><span class="sxs-lookup"><span data-stu-id="ef771-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="ef771-112">Vererbungsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="ef771-112">Inheritance Modifiers</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="ef771-113">führt die folgenden auf Klassenebene-Anweisungen und Modifizierer für die Vererbung unterstützen:</span><span class="sxs-lookup"><span data-stu-id="ef771-113"> introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
-   <span data-ttu-id="ef771-114">`Inherits`Anweisung: Gibt die Basisklasse an.</span><span class="sxs-lookup"><span data-stu-id="ef771-114">`Inherits` statement — Specifies the base class.</span></span>  
  
-   <span data-ttu-id="ef771-115">`NotInheritable`Modifizierer – verhindert, dass Programmierer die Klasse als Basisklasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef771-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
-   <span data-ttu-id="ef771-116">`MustInherit`Modifizierer – gibt an, dass die Klasse nur als Basisklasse verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef771-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="ef771-117">Instanzen von `MustInherit` Klassen können nicht direkt erstellt werden; sie können nur erstellt werden als base Klasseninstanzen einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="ef771-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="ef771-118">(Andere Programmiersprachen wie C++ und c# verwenden den Begriff *abstrakte Klasse* um eine solche Klasse zu beschreiben.)</span><span class="sxs-lookup"><span data-stu-id="ef771-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="ef771-119">Überschreiben von Eigenschaften und Methoden in abgeleiteten Klassen</span><span class="sxs-lookup"><span data-stu-id="ef771-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="ef771-120">Standardmäßig erbt eine abgeleitete Klasse Eigenschaften und Methoden von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="ef771-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="ef771-121">Besitzt eine geerbte Eigenschaft oder Methode in der abgeleiteten Klasse anders Verhalten möglich *überschreiben*.</span><span class="sxs-lookup"><span data-stu-id="ef771-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="ef771-122">Das heißt, können Sie eine neue Implementierung der Methode in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="ef771-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="ef771-123">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="ef771-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
-   <span data-ttu-id="ef771-124">`Overridable`– Ermöglicht eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ef771-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
-   <span data-ttu-id="ef771-125">`Overrides`– Überschreibt eine `Overridable` Eigenschaft oder Methode in der Basisklasse definiert.</span><span class="sxs-lookup"><span data-stu-id="ef771-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
-   <span data-ttu-id="ef771-126">`NotOverridable`– Verhindert, dass eine Eigenschaft oder Methode in einer erbenden Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="ef771-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="ef771-127">In der Standardeinstellung `Public` Methoden sind `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="ef771-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
-   <span data-ttu-id="ef771-128">`MustOverride`– Muss eine abgeleitete Klasse überschreiben, die Eigenschaft oder Methode.</span><span class="sxs-lookup"><span data-stu-id="ef771-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="ef771-129">Wenn die `MustOverride` Schlüsselwort verwendet wird, besteht aus der Definition der Methode lediglich die `Sub`, `Function`, oder `Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ef771-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="ef771-130">Keine weiteren Anweisungen sind zulässig, und insbesondere ist keine `End Sub` oder `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ef771-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="ef771-131">`MustOverride`Methoden müssen deklariert werden, `MustInherit` Klassen.</span><span class="sxs-lookup"><span data-stu-id="ef771-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="ef771-132">Angenommen Sie, Sie möchten zum Definieren von Klassen, um die Gehaltsliste zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ef771-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="ef771-133">Sie definieren eine generische `Payroll` Klasse enthält eine `RunPayroll` -Methode, die Gehaltsdaten für eine normale Woche berechnet.</span><span class="sxs-lookup"><span data-stu-id="ef771-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="ef771-134">Sie können dann `Payroll` als Basisklasse für eine spezielle `BonusPayroll` -Klasse, die beim Verteilen der Mitarbeiterboni verwendet.</span><span class="sxs-lookup"><span data-stu-id="ef771-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="ef771-135">Die `BonusPayroll` Klasse erben und außer Kraft setzen, kann der `PayEmployee` in der Basisklasse definierte Methode `Payroll` Klasse.</span><span class="sxs-lookup"><span data-stu-id="ef771-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="ef771-136">Das folgende Beispiel definiert eine Basisklasse `Payroll,` und einer abgeleiteten Klasse `BonusPayroll`, die eine geerbte Methode, überschreibt `PayEmployee`.</span><span class="sxs-lookup"><span data-stu-id="ef771-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="ef771-137">Eine Prozedur `RunPayroll`, erstellt und übergibt eine `Payroll` Objekt und ein `BonusPayroll` -Objekt an eine Funktion `Pay`, ausgeführt wird, die `PayEmployee` -Methode beider Objekte.</span><span class="sxs-lookup"><span data-stu-id="ef771-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 <span data-ttu-id="ef771-138">[!code-vb[VbVbalrOOP&#28;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ef771-138">[!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]</span></span>  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="ef771-139">MyBase-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="ef771-139">The MyBase Keyword</span></span>  
 <span data-ttu-id="ef771-140">Das `MyBase` -Schlüsselwort verhält sich wie eine Objektvariable, die auf die Basisklasse der aktuellen Instanz einer Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="ef771-140">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="ef771-141">`MyBase`Member der Basisklasse zugreifen, die überschrieben werden, oder in einer abgeleiteten Klasse gespiegelt wird häufig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef771-141">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="ef771-142">Insbesondere `MyBase.New` wird verwendet, um einen Basisklassenkonstruktor aus einem abgeleiteten Klassenkonstruktor explizit aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="ef771-142">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="ef771-143">Nehmen wir beispielsweise an, dass Sie eine abgeleitete Klasse entwerfen, die eine von der Basisklasse geerbten Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="ef771-143">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="ef771-144">Die überschriebene Methode kann die Methode in der Basisklasse aufrufen und den Rückgabewert zu ändern, wie im folgenden Codefragment gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ef771-144">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 <span data-ttu-id="ef771-145">[!code-vb[VbVbalrOOP&#109;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ef771-145">[!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]</span></span>  
  
 <span data-ttu-id="ef771-146">Die folgende Liste beschreibt die Einschränkungen zur Verwendung von `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="ef771-146">The following list describes restrictions on using `MyBase`:</span></span>  
  
-   <span data-ttu-id="ef771-147">`MyBase`bezieht sich auf die unmittelbare Basisklasse und deren geerbte Member.</span><span class="sxs-lookup"><span data-stu-id="ef771-147">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="ef771-148">Kann nicht verwendet werden für den Zugriff auf `Private` Member in der Klasse.</span><span class="sxs-lookup"><span data-stu-id="ef771-148">It cannot be used to access `Private` members in the class.</span></span>  
  
-   <span data-ttu-id="ef771-149">`MyBase`ist ein Schlüsselwort, kein wirkliches Objekt.</span><span class="sxs-lookup"><span data-stu-id="ef771-149">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="ef771-150">`MyBase`einer Variablen zugewiesen, in der Prozedur zu übergeben oder in verwendet werden kann kein `Is` Vergleich.</span><span class="sxs-lookup"><span data-stu-id="ef771-150">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="ef771-151">Die Methode, die `MyBase` qualifiziert muss nicht in der unmittelbaren Basisklasse; definiert werden sie möglicherweise stattdessen in einer indirekt geerbten Basisklasse definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ef771-151">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="ef771-152">Ein Verweis von qualifizierten `MyBase` ordnungsgemäß kompiliert wird, muss die Basisklasse enthalten einer Methode mit dem Namen und Typen der Parameter, die im Aufruf angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ef771-152">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
-   <span data-ttu-id="ef771-153">Sie können keine `MyBase` Aufrufen `MustOverride` Klassenmethoden basieren.</span><span class="sxs-lookup"><span data-stu-id="ef771-153">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
-   <span data-ttu-id="ef771-154">`MyBase`kann verwendet werden, um sich selbst zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="ef771-154">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="ef771-155">Daher ist der folgende Code ungültig:</span><span class="sxs-lookup"><span data-stu-id="ef771-155">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   <span data-ttu-id="ef771-156">`MyBase`kann nicht in Modulen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef771-156">`MyBase` cannot be used in modules.</span></span>  
  
-   <span data-ttu-id="ef771-157">`MyBase`kann nicht verwendet werden, um den Zugriff auf Basisklassenmember, die als markiert sind `Friend` ist die Basisklasse in einer anderen Assembly.</span><span class="sxs-lookup"><span data-stu-id="ef771-157">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="ef771-158">Weitere Informationen und ein weiteres Beispiel finden Sie unter [Gewusst wie: Zugriff auf eine Variable Hidden durch eine abgeleitete Klasse](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="ef771-158">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="ef771-159">MyClass-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="ef771-159">The MyClass Keyword</span></span>  
 <span data-ttu-id="ef771-160">Das `MyClass` -Schlüsselwort verhält sich wie eine Objektvariable, die auf die aktuelle Instanz einer Klasse, die gemäß der ursprünglichen Implementierung verweist.</span><span class="sxs-lookup"><span data-stu-id="ef771-160">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="ef771-161">`MyClass`ähnelt `Me`, aber alle Methoden und Eigenschaften, die in Aufrufen `MyClass` wird behandelt, als wäre die Methode oder Eigenschaft [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="ef771-161">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="ef771-162">Aus diesem Grund ist die Methode oder Eigenschaft nicht betroffen in einer abgeleiteten Klasse überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ef771-162">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
-   <span data-ttu-id="ef771-163">`MyClass`ist ein Schlüsselwort, kein wirkliches Objekt.</span><span class="sxs-lookup"><span data-stu-id="ef771-163">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="ef771-164">`MyClass`einer Variablen zugewiesen, in der Prozedur zu übergeben oder in verwendet werden kann kein `Is` Vergleich.</span><span class="sxs-lookup"><span data-stu-id="ef771-164">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="ef771-165">`MyClass`bezieht sich auf die enthaltene Klasse und deren geerbte Member.</span><span class="sxs-lookup"><span data-stu-id="ef771-165">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
-   <span data-ttu-id="ef771-166">`MyClass`kann verwendet werden, als Qualifizierer für `Shared` Elemente.</span><span class="sxs-lookup"><span data-stu-id="ef771-166">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
-   <span data-ttu-id="ef771-167">`MyClass`kann nicht verwendet werden, in eine `Shared` -Methode, aber innerhalb einer Instanzmethode Zugriff auf einen freigegebenen Member einer Klasse verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ef771-167">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
-   <span data-ttu-id="ef771-168">`MyClass`kann nicht in Standardmodulen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef771-168">`MyClass` cannot be used in standard modules.</span></span>  
  
-   <span data-ttu-id="ef771-169">`MyClass`kann verwendet werden, qualifizieren Sie eine Methode in einer Basisklasse definiert ist und die keine Implementierung der in dieser Klasse enthaltenen Methode aufweist.</span><span class="sxs-lookup"><span data-stu-id="ef771-169">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="ef771-170">Durch einen solchen Verweis hat dieselbe Bedeutung wie `MyBase.` *Methode*.</span><span class="sxs-lookup"><span data-stu-id="ef771-170">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="ef771-171">Im folgenden Beispiel werden `Me` und `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="ef771-171">The following example compares `Me` and `MyClass`.</span></span>  
  
```vb
Class baseClass  
    Public Overridable Sub testMethod()  
        MsgBox("Base class string")  
    End Sub  
    Public Sub useMe()  
        ' The following call uses the calling class's method, even if   
        ' that method is an override.  
        Me.testMethod()  
    End Sub  
    Public Sub useMyClass()  
        ' The following call uses this instance's method and not any  
        ' override.  
        MyClass.testMethod()  
    End Sub  
End Class  
Class derivedClass : Inherits baseClass  
    Public Overrides Sub testMethod()  
        MsgBox("Derived class string")  
    End Sub  
End Class  
Class testClasses  
    Sub startHere()  
        Dim testObj As derivedClass = New derivedClass()  
        ' The following call displays "Derived class string".  
        testObj.useMe()  
        ' The following call displays "Base class string".  
        testObj.useMyClass()  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="ef771-172">Obwohl `derivedClass` überschreibt `testMethod`, `MyClass` Schlüsselwort in `useMyClass` wird überschrieben, und der Compiler löst den Aufruf von die Basisklassenversion von `testMethod`.</span><span class="sxs-lookup"><span data-stu-id="ef771-172">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef771-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef771-173">See Also</span></span>  
 <span data-ttu-id="ef771-174">[Inherits-Anweisung](../../../../visual-basic/language-reference/statements/inherits-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ef771-174">[Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md) </span></span>  
<span data-ttu-id="ef771-175"> [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="ef771-175"> [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>

