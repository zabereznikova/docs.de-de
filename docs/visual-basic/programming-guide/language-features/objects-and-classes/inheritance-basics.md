---
title: Grundlagen der Vererbung (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76813bb36c0bcf75791932a0fec081f0fc1958e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="939c6-102">Grundlagen der Vererbung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="939c6-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="939c6-103">Die `Inherits` Anweisung wird verwendet, um eine neue Klasse mit dem Namen zu deklarieren einer *abgeleitete Klasse*basierend auf einer vorhandenen Klasse, die als bezeichnet eine *Basisklasse*.</span><span class="sxs-lookup"><span data-stu-id="939c6-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="939c6-104">Abgeleitete Klassen erben, und erweitern können, die Eigenschaften, Methoden, Ereignisse, Felder und Konstanten, die in der Basisklasse definiert.</span><span class="sxs-lookup"><span data-stu-id="939c6-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="939c6-105">Der folgende Abschnitt beschreibt einige der Regeln für die Vererbung, und der Modifizierer, die Sie verwenden können, so ändern Sie die Möglichkeit Klassen erben oder geerbt werden:</span><span class="sxs-lookup"><span data-stu-id="939c6-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
-   <span data-ttu-id="939c6-106">Standardmäßig alle Klassen geerbt, es sei denn, die mit gekennzeichnet werden die `NotInheritable` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="939c6-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="939c6-107">Klassen können von anderen Klassen in Ihrem Projekt oder von Klassen in anderen Assemblys, die das Projekt verweist auf erben.</span><span class="sxs-lookup"><span data-stu-id="939c6-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
-   <span data-ttu-id="939c6-108">Im Gegensatz zu den Sprachen, die mehrfache Vererbung ermöglichen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] können nur einfache Vererbung in Klassen; d. h. abgeleitete Klassen können nur eine Basisklasse haben.</span><span class="sxs-lookup"><span data-stu-id="939c6-108">Unlike languages that allow multiple inheritance, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="939c6-109">Jedoch in Klassen keine mehrfache Vererbung zulässig ist, können Klassen mehrere Schnittstellen implementieren, die effektiv die gleichen enden ausführen können.</span><span class="sxs-lookup"><span data-stu-id="939c6-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
-   <span data-ttu-id="939c6-110">Um zu verhindern, eingeschränkte Elemente in einer Basisklasse verfügbar machen, muss von einer abgeleiteten Klasse der Zugriffstyp restriktiver ist als seine Basisklasse oder gleich sein.</span><span class="sxs-lookup"><span data-stu-id="939c6-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="939c6-111">Z. B. eine `Public` Klasse kann nicht geerbt werden eine `Friend` oder ein `Private` -Klasse, und ein `Friend` Klasse kann nicht geerbt werden eine `Private` Klasse.</span><span class="sxs-lookup"><span data-stu-id="939c6-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="939c6-112">Von Vererbungsmodifizierern</span><span class="sxs-lookup"><span data-stu-id="939c6-112">Inheritance Modifiers</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="939c6-113">führt die folgenden Anweisungen aus auf Klassenebene und -Modifizierern zur Unterstützung der Vererbung:</span><span class="sxs-lookup"><span data-stu-id="939c6-113"> introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
-   <span data-ttu-id="939c6-114">`Inherits`Anweisung – gibt die Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="939c6-114">`Inherits` statement — Specifies the base class.</span></span>  
  
-   <span data-ttu-id="939c6-115">`NotInheritable`Modifizierer – verhindert, dass Programmierer die Klasse als Basisklasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="939c6-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
-   <span data-ttu-id="939c6-116">`MustInherit`Modifizierer – gibt an, dass die Klasse zur Verwendung als Basisklasse nur vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="939c6-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="939c6-117">Instanzen von `MustInherit` Klassen können nicht direkt erstellt werden; sie können nur erstellt werden als base Klasseninstanzen einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="939c6-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="939c6-118">(Anderer Programmiersprachen vergleichbar, z. B. C++ und c#, mithilfe des Begriffs *abstrakte Klasse* um eine solche Klasse zu beschreiben.)</span><span class="sxs-lookup"><span data-stu-id="939c6-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="939c6-119">Überschreiben von Eigenschaften und Methoden in abgeleiteten Klassen</span><span class="sxs-lookup"><span data-stu-id="939c6-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="939c6-120">Standardmäßig erbt eine abgeleitete Klasse Eigenschaften und Methoden von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="939c6-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="939c6-121">Besitzt eine geerbte Eigenschaft oder Methode in der abgeleiteten Klasse unterschiedlich Verhalten möglich *überschreiben*.</span><span class="sxs-lookup"><span data-stu-id="939c6-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="939c6-122">Das heißt, können Sie eine neue Implementierung der Methode in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="939c6-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="939c6-123">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="939c6-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
-   <span data-ttu-id="939c6-124">`Overridable`– Ermöglicht einer Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="939c6-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
-   <span data-ttu-id="939c6-125">`Overrides`– Überschreibt eine `Overridable` Eigenschaft oder Methode in der Basisklasse definiert.</span><span class="sxs-lookup"><span data-stu-id="939c6-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
-   <span data-ttu-id="939c6-126">`NotOverridable`– Verhindert, dass eine Eigenschaft oder Methode in einer erbenden Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="939c6-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="939c6-127">Standardmäßig `Public` Methoden sind `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="939c6-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
-   <span data-ttu-id="939c6-128">`MustOverride`– Erfordert, dass es sich bei eine abgeleitete Klasse außer Kraft setzen der Eigenschaft oder Methode.</span><span class="sxs-lookup"><span data-stu-id="939c6-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="939c6-129">Wenn die `MustOverride` Schlüsselwort verwendet wird, besteht die Methodendefinition nur die `Sub`, `Function`, oder `Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="939c6-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="939c6-130">Keine weiteren Anweisungen sind zulässig und insbesondere besteht keine `End Sub` oder `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="939c6-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="939c6-131">`MustOverride`Methoden müssen deklariert werden, `MustInherit` Klassen.</span><span class="sxs-lookup"><span data-stu-id="939c6-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="939c6-132">Angenommen Sie, Sie definieren von Klassen, um Gehaltsdaten verarbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="939c6-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="939c6-133">Sie können einen generischen definieren `Payroll` Klasse enthält eine `RunPayroll` Methode, die für eine typische Woche Payroll berechnet.</span><span class="sxs-lookup"><span data-stu-id="939c6-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="939c6-134">Anschließend können Sie `Payroll` als Basisklasse für ein spezialisierter `BonusPayroll` -Klasse, die verwendet werden können, wenn Mitarbeiterboni verteilt.</span><span class="sxs-lookup"><span data-stu-id="939c6-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="939c6-135">Die `BonusPayroll` Klasse erben kann, und überschreiben die `PayEmployee` in der Basisklasse definierte Methode `Payroll` Klasse.</span><span class="sxs-lookup"><span data-stu-id="939c6-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="939c6-136">Das folgende Beispiel definiert eine Basisklasse `Payroll,` und eine abgeleitete Klasse `BonusPayroll`, die eine geerbte Methode überschreibt `PayEmployee`.</span><span class="sxs-lookup"><span data-stu-id="939c6-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="939c6-137">Eine Prozedur `RunPayroll`, erstellt und übergibt dann eine `Payroll` Objekt und ein `BonusPayroll` -Objekt an eine Funktion `Pay`, ausführt, die `PayEmployee` -Methode der beiden Objekte.</span><span class="sxs-lookup"><span data-stu-id="939c6-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="939c6-138">MyBase-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="939c6-138">The MyBase Keyword</span></span>  
 <span data-ttu-id="939c6-139">Die `MyBase` Schlüsselwort verhält sich wie eine Objektvariable, die auf die Basisklasse der aktuellen Instanz einer Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="939c6-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="939c6-140">`MyBase`Member der Basisklasse zuzugreifen, die überschrieben werden, oder in einer abgeleiteten Klasse schattiert wird häufig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="939c6-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="939c6-141">Insbesondere `MyBase.New` wird verwendet, um explizit einen Basisklassenkonstruktor vom Konstruktor einer abgeleiteten Klasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="939c6-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="939c6-142">Nehmen Sie beispielsweise an, dass Sie eine abgeleitete Klasse entwerfen, die eine Methode, die von der Basisklasse vererbt überschreibt.</span><span class="sxs-lookup"><span data-stu-id="939c6-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="939c6-143">Die überschriebene Methode kann die Methode in der Basisklasse aufrufen und den Rückgabewert zu ändern, wie im folgenden Codefragment gezeigt:</span><span class="sxs-lookup"><span data-stu-id="939c6-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 <span data-ttu-id="939c6-144">Die folgende Liste beschreibt die Einschränkungen zur Verwendung von `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="939c6-144">The following list describes restrictions on using `MyBase`:</span></span>  
  
-   <span data-ttu-id="939c6-145">`MyBase`bezieht sich auf die unmittelbare Basisklasse und deren geerbte Member.</span><span class="sxs-lookup"><span data-stu-id="939c6-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="939c6-146">Kann nicht verwendet werden für den Zugriff auf `Private` Member in der Klasse.</span><span class="sxs-lookup"><span data-stu-id="939c6-146">It cannot be used to access `Private` members in the class.</span></span>  
  
-   <span data-ttu-id="939c6-147">`MyBase`ist ein Schlüsselwort, kein echtes Objekt.</span><span class="sxs-lookup"><span data-stu-id="939c6-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="939c6-148">`MyBase`einer Variablen zugewiesen, in der Prozedur zu übergeben oder verwendet werden kann kein `Is` Vergleich.</span><span class="sxs-lookup"><span data-stu-id="939c6-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="939c6-149">Die Methode, die `MyBase` qualifiziert keinen direkten Basisklasse; definiert werden möglicherweise stattdessen in einer indirekt geerbte Basisklasse definiert werden.</span><span class="sxs-lookup"><span data-stu-id="939c6-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="939c6-150">Ein Verweis von qualifizierten `MyBase` um ordnungsgemäß zu kompilieren, einige Basisklasse muss eine Methode enthalten den Namen und Typen der Parameter, die im Aufruf angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="939c6-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
-   <span data-ttu-id="939c6-151">Sie können keine `MyBase` Aufrufen `MustOverride` -Klasse, Methoden basieren.</span><span class="sxs-lookup"><span data-stu-id="939c6-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
-   <span data-ttu-id="939c6-152">`MyBase`kann nicht verwendet werden, um sich selbst zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="939c6-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="939c6-153">Aus diesem Grund ist der folgende Code ungültig:</span><span class="sxs-lookup"><span data-stu-id="939c6-153">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   <span data-ttu-id="939c6-154">`MyBase`kann nicht in Modulen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="939c6-154">`MyBase` cannot be used in modules.</span></span>  
  
-   <span data-ttu-id="939c6-155">`MyBase`kann nicht verwendet werden, um Zugriff auf Basisklassenmember, die als markiert sind `Friend` ist die Basisklasse in einer anderen Assembly.</span><span class="sxs-lookup"><span data-stu-id="939c6-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="939c6-156">Weitere Informationen und ein weiteres Beispiel finden Sie unter [Vorgehensweise: Zugriff auf eine Variable Hidden durch eine abgeleitete Klasse](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="939c6-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="939c6-157">MyClass-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="939c6-157">The MyClass Keyword</span></span>  
 <span data-ttu-id="939c6-158">Die `MyClass` Schlüsselwort verhält sich wie eine Objektvariable, die auf die aktuelle Instanz einer Klasse, die als ursprünglich verweist.</span><span class="sxs-lookup"><span data-stu-id="939c6-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="939c6-159">`MyClass`ähnelt `Me`, aber alle Methoden und Eigenschaften, die in Aufrufen `MyClass` wird behandelt, als wäre die Methode oder Eigenschaft [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="939c6-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="939c6-160">Aus diesem Grund ist die Methode oder Eigenschaft nicht betroffen von in einer abgeleiteten Klasse überschreiben.</span><span class="sxs-lookup"><span data-stu-id="939c6-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
-   <span data-ttu-id="939c6-161">`MyClass`ist ein Schlüsselwort, kein echtes Objekt.</span><span class="sxs-lookup"><span data-stu-id="939c6-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="939c6-162">`MyClass`einer Variablen zugewiesen, in der Prozedur zu übergeben oder verwendet werden kann kein `Is` Vergleich.</span><span class="sxs-lookup"><span data-stu-id="939c6-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="939c6-163">`MyClass`bezieht sich auf die enthaltende Klasse und deren geerbte Member.</span><span class="sxs-lookup"><span data-stu-id="939c6-163">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
-   <span data-ttu-id="939c6-164">`MyClass`Dient als Qualifizierer für `Shared` Elemente.</span><span class="sxs-lookup"><span data-stu-id="939c6-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
-   <span data-ttu-id="939c6-165">`MyClass`kann nicht verwendet werden, in einem `Shared` -Methode, jedoch können in einer Instanzmethode verwendet werden, um einen freigegebenen Member einer Klasse zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="939c6-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
-   <span data-ttu-id="939c6-166">`MyClass`kann nicht in standard-Modulen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="939c6-166">`MyClass` cannot be used in standard modules.</span></span>  
  
-   <span data-ttu-id="939c6-167">`MyClass`kann verwendet werden, auf eine Methode, die in einer Basisklasse definiert ist, und ohne Implementierung der Methode in dieser Klasse bereitgestellten, kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="939c6-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="939c6-168">Durch einen solchen Verweis hat die gleiche Bedeutung wie `MyBase.` *Methode*.</span><span class="sxs-lookup"><span data-stu-id="939c6-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="939c6-169">Das folgende Beispiel vergleicht `Me` und `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="939c6-169">The following example compares `Me` and `MyClass`.</span></span>  
  
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
  
 <span data-ttu-id="939c6-170">Obwohl `derivedClass` überschreibt `testMethod`, `MyClass` -Schlüsselwort in `useMyClass` hebt den Auswirkungen der überschreiben, und der Compiler löst den Aufruf die Basisklassenversion von `testMethod`.</span><span class="sxs-lookup"><span data-stu-id="939c6-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="939c6-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="939c6-171">See Also</span></span>  
 [<span data-ttu-id="939c6-172">Inherits-Anweisung</span><span class="sxs-lookup"><span data-stu-id="939c6-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="939c6-173">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="939c6-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
