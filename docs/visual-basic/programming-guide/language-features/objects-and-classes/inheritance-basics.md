---
title: Grundlagen der Vererbung
ms.date: 07/20/2015
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
ms.openlocfilehash: 3bf1847f618a642d26df4aa1c5247a4ba2bd3b23
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411778"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="243bb-102">Grundlagen der Vererbung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="243bb-102">Inheritance Basics (Visual Basic)</span></span>

<span data-ttu-id="243bb-103">Die- `Inherits` Anweisung wird verwendet, um eine neue Klasse, die als *abgeleitete Klasse*bezeichnet wird, auf Grundlage einer vorhandenen Klasse, die als *Basisklasse*bezeichnet wird, zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="243bb-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="243bb-104">Abgeleitete Klassen erben die Eigenschaften, Methoden, Ereignisse, Felder und Konstanten, die in der Basisklasse definiert sind, und können Sie erweitern.</span><span class="sxs-lookup"><span data-stu-id="243bb-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="243bb-105">Im folgenden Abschnitt werden einige der Vererbungs Regeln und die Modifizierer beschrieben, die Sie verwenden können, um die Art und Weise zu ändern, in der Klassen geerbt oder geerbt werden:</span><span class="sxs-lookup"><span data-stu-id="243bb-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>

- <span data-ttu-id="243bb-106">Standardmäßig sind alle Klassen vererbbar, sofern Sie nicht mit dem- `NotInheritable` Schlüsselwort gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="243bb-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="243bb-107">Klassen können von anderen Klassen in Ihrem Projekt oder von Klassen in anderen Assemblys erben, auf die Ihr Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="243bb-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>

- <span data-ttu-id="243bb-108">Im Unterschied zu Sprachen, die mehrere Vererbung zulassen, Visual Basic nur die einfache Vererbung in Klassen zulässt. Das heißt, dass abgeleitete Klassen nur eine Basisklasse haben können.</span><span class="sxs-lookup"><span data-stu-id="243bb-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="243bb-109">Obwohl die mehrfache Vererbung in Klassen nicht zulässig ist, können Klassen mehrere Schnittstellen implementieren, die die gleichen enden effektiv erreichen können.</span><span class="sxs-lookup"><span data-stu-id="243bb-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>

- <span data-ttu-id="243bb-110">Um zu verhindern, dass eingeschränkte Elemente in einer Basisklasse verfügbar gemacht werden, muss der Zugriffstyp einer abgeleiteten Klasse gleich oder restriktiver sein als die Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="243bb-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="243bb-111">Eine Klasse kann z. b `Public` . weder eine `Friend` -Klasse noch eine-Klasse erben `Private` , und eine Klasse `Friend` kann keine Klasse erben `Private` .</span><span class="sxs-lookup"><span data-stu-id="243bb-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>

## <a name="inheritance-modifiers"></a><span data-ttu-id="243bb-112">Vererbungs Modifizierer</span><span class="sxs-lookup"><span data-stu-id="243bb-112">Inheritance Modifiers</span></span>

<span data-ttu-id="243bb-113">Visual Basic führt die folgenden Klassen-und Modifizierer auf Klassenebene ein, um Vererbung zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="243bb-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>

- <span data-ttu-id="243bb-114">`Inherits`Anweisung – gibt die Basisklasse an.</span><span class="sxs-lookup"><span data-stu-id="243bb-114">`Inherits` statement — Specifies the base class.</span></span>

- <span data-ttu-id="243bb-115">`NotInheritable`Modifizierer – verhindert, dass Programmierer die Klasse als Basisklasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="243bb-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>

- <span data-ttu-id="243bb-116">`MustInherit`Modifizierer – gibt an, dass die Klasse nur als Basisklasse verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="243bb-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="243bb-117">Instanzen von `MustInherit` Klassen können nicht direkt erstellt werden. Sie können nur als Basisklassen Instanzen einer abgeleiteten Klasse erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="243bb-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="243bb-118">(Andere Programmiersprachen, wie z. b. C++ und c#, verwenden den Begriff *abstrakte Klasse* , um eine solche Klasse zu beschreiben.)</span><span class="sxs-lookup"><span data-stu-id="243bb-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>

## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="243bb-119">Überschreiben von Eigenschaften und Methoden in abgeleiteten Klassen</span><span class="sxs-lookup"><span data-stu-id="243bb-119">Overriding Properties and Methods in Derived Classes</span></span>

<span data-ttu-id="243bb-120">Standardmäßig erbt eine abgeleitete Klasse Eigenschaften und Methoden von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="243bb-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="243bb-121">Wenn eine geerbte Eigenschaft oder Methode in der abgeleiteten Klasse anders Verhalten muss, kann Sie *überschrieben*werden.</span><span class="sxs-lookup"><span data-stu-id="243bb-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="243bb-122">Das heißt, Sie können eine neue Implementierung der-Methode in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="243bb-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="243bb-123">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="243bb-123">The following modifiers are used to control how properties and methods are overridden:</span></span>

- <span data-ttu-id="243bb-124">`Overridable`– Ermöglicht, dass eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="243bb-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>

- <span data-ttu-id="243bb-125">`Overrides`– Überschreibt eine `Overridable` Eigenschaft oder Methode, die in der Basisklasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="243bb-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>

- <span data-ttu-id="243bb-126">`NotOverridable`– Verhindert, dass eine Eigenschaft oder Methode in einer erbenden Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="243bb-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="243bb-127">Standardmäßig `Public` sind Methoden `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="243bb-127">By default, `Public` methods are `NotOverridable`.</span></span>

- <span data-ttu-id="243bb-128">`MustOverride`– Erfordert, dass eine abgeleitete Klasse die-Eigenschaft oder die-Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="243bb-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="243bb-129">Wenn das- `MustOverride` Schlüsselwort verwendet wird, besteht die-Methoden Definition nur aus der- `Sub` ,-oder- `Function` `Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="243bb-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="243bb-130">Es sind keine weiteren Anweisungen zulässig, und es ist keine- `End Sub` oder- `End Function` Anweisung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="243bb-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="243bb-131">`MustOverride`Methoden müssen in Klassen deklariert werden `MustInherit` .</span><span class="sxs-lookup"><span data-stu-id="243bb-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>

<span data-ttu-id="243bb-132">Angenommen, Sie möchten Klassen definieren, um die Gehaltsabrechnung zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="243bb-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="243bb-133">Sie können eine generische `Payroll` Klasse definieren, die eine `RunPayroll` Methode enthält, die eine Abrechnung für eine typische Woche berechnet.</span><span class="sxs-lookup"><span data-stu-id="243bb-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="243bb-134">Anschließend können Sie `Payroll` als Basisklasse für eine speziellere Klasse verwenden `BonusPayroll` , die bei der Verteilung von Mitarbeiter-Boni verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="243bb-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>

<span data-ttu-id="243bb-135">Die `BonusPayroll` Klasse kann die `PayEmployee` in der Basisklasse definierte Methode erben und überschreiben `Payroll` .</span><span class="sxs-lookup"><span data-stu-id="243bb-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>

<span data-ttu-id="243bb-136">Im folgenden Beispiel wird eine Basisklasse `Payroll,` und eine abgeleitete Klasse definiert, `BonusPayroll` die eine geerbte Methode überschreibt `PayEmployee` .</span><span class="sxs-lookup"><span data-stu-id="243bb-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="243bb-137">Eine Prozedur, `RunPayroll` , erstellt und übergibt ein `Payroll` -Objekt und ein- `BonusPayroll` Objekt an eine Funktion,, die die-Methode beider- `Pay` `PayEmployee` Objekte ausführt.</span><span class="sxs-lookup"><span data-stu-id="243bb-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a><span data-ttu-id="243bb-138">Das MyBase-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="243bb-138">The MyBase Keyword</span></span>

<span data-ttu-id="243bb-139">Das- `MyBase` Schlüsselwort verhält sich wie eine Objekt Variable, die auf die Basisklasse der aktuellen Instanz einer-Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="243bb-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="243bb-140">`MyBase`wird häufig verwendet, um auf Basisklassenmember zuzugreifen, die von einer abgeleiteten Klasse überschrieben oder überschattet werden.</span><span class="sxs-lookup"><span data-stu-id="243bb-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="243bb-141">Insbesondere `MyBase.New` wird verwendet, um explizit einen Basisklassenkonstruktor aus einem abgeleiteten Klassenkonstruktor aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="243bb-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>

<span data-ttu-id="243bb-142">Angenommen, Sie entwerfen eine abgeleitete Klasse, die eine Methode überschreibt, die von der Basisklasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="243bb-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="243bb-143">Die überschriebene-Methode kann die-Methode in der Basisklasse aufrufen und den Rückgabewert ändern, wie im folgenden Code Fragment gezeigt:</span><span class="sxs-lookup"><span data-stu-id="243bb-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

<span data-ttu-id="243bb-144">In der folgenden Liste werden die Einschränkungen der Verwendung von beschrieben `MyBase` :</span><span class="sxs-lookup"><span data-stu-id="243bb-144">The following list describes restrictions on using `MyBase`:</span></span>

- <span data-ttu-id="243bb-145">`MyBase`verweist auf die unmittelbare Basisklasse und die geerbten Member.</span><span class="sxs-lookup"><span data-stu-id="243bb-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="243bb-146">Sie kann nicht verwendet werden, um auf Member `Private` in der-Klasse zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="243bb-146">It cannot be used to access `Private` members in the class.</span></span>

- <span data-ttu-id="243bb-147">`MyBase`ist ein Schlüsselwort, kein reales Objekt.</span><span class="sxs-lookup"><span data-stu-id="243bb-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="243bb-148">`MyBase`kann keiner Variablen zugewiesen werden, an Prozeduren übermittelt oder in einem `Is` Vergleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="243bb-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="243bb-149">Die Methode, die `MyBase` qualifiziert, muss nicht in der unmittelbaren Basisklasse definiert werden. stattdessen kann Sie in einer indirekt geerbten Basisklasse definiert werden.</span><span class="sxs-lookup"><span data-stu-id="243bb-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="243bb-150">Damit ein von qualifizierter Verweis `MyBase` ordnungsgemäß kompiliert werden kann, muss eine Basisklasse eine Methode enthalten, die mit dem Namen und den Typen von Parametern übereinstimmt, die im-Befehl angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="243bb-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>

- <span data-ttu-id="243bb-151">Sie können nicht verwenden `MyBase` , um `MustOverride` Basisklassen Methoden aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="243bb-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>

- <span data-ttu-id="243bb-152">`MyBase`kann nicht verwendet werden, um sich selbst zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="243bb-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="243bb-153">Daher ist der folgende Code nicht gültig:</span><span class="sxs-lookup"><span data-stu-id="243bb-153">Therefore, the following code is not valid:</span></span>

  `MyBase.MyBase.BtnOK_Click()`

- <span data-ttu-id="243bb-154">`MyBase`kann nicht in Modulen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="243bb-154">`MyBase` cannot be used in modules.</span></span>

- <span data-ttu-id="243bb-155">`MyBase`kann nicht für den Zugriff auf Basisklassenmember verwendet werden, die als gekennzeichnet sind, `Friend` Wenn die Basisklasse in einer anderen Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="243bb-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>

<span data-ttu-id="243bb-156">Weitere Informationen und ein weiteres Beispiel finden Sie unter Gewusst [wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet](../declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)wird.</span><span class="sxs-lookup"><span data-stu-id="243bb-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>

## <a name="the-myclass-keyword"></a><span data-ttu-id="243bb-157">Das Schlüsselwort "MyClass"</span><span class="sxs-lookup"><span data-stu-id="243bb-157">The MyClass Keyword</span></span>

<span data-ttu-id="243bb-158">Das- `MyClass` Schlüsselwort verhält sich wie eine Objekt Variable, die auf die aktuelle Instanz einer Klasse verweist, die ursprünglich implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="243bb-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="243bb-159">`MyClass`ähnelt `Me` , aber jeder Methoden-und Eigenschafts Rückruf für `MyClass` wird so behandelt, als ob die Methode oder Eigenschaft [nodeverridable](../../../language-reference/modifiers/notoverridable.md)wäre.</span><span class="sxs-lookup"><span data-stu-id="243bb-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="243bb-160">Daher wird die-Methode oder-Eigenschaft nicht durch das Überschreiben in einer abgeleiteten Klasse beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="243bb-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>

- <span data-ttu-id="243bb-161">`MyClass`ist ein Schlüsselwort, kein reales Objekt.</span><span class="sxs-lookup"><span data-stu-id="243bb-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="243bb-162">`MyClass`kann keiner Variablen zugewiesen werden, an Prozeduren übermittelt oder in einem `Is` Vergleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="243bb-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="243bb-163">`MyClass`verweist auf die enthaltende Klasse und die geerbten Member.</span><span class="sxs-lookup"><span data-stu-id="243bb-163">`MyClass` refers to the containing class and its inherited members.</span></span>

- <span data-ttu-id="243bb-164">`MyClass`kann als Qualifizierer für Member verwendet werden `Shared` .</span><span class="sxs-lookup"><span data-stu-id="243bb-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>

- <span data-ttu-id="243bb-165">`MyClass`kann nicht innerhalb einer Methode verwendet werden `Shared` , kann jedoch innerhalb einer Instanzmethode verwendet werden, um auf einen freigegebenen Member einer Klasse zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="243bb-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>

- <span data-ttu-id="243bb-166">`MyClass`kann nicht in Standardmodulen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="243bb-166">`MyClass` cannot be used in standard modules.</span></span>

- <span data-ttu-id="243bb-167">`MyClass`kann verwendet werden, um eine Methode zu qualifizieren, die in einer Basisklasse definiert ist und die über keine Implementierung der in dieser Klasse bereitgestellten Methode verfügt.</span><span class="sxs-lookup"><span data-stu-id="243bb-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="243bb-168">Ein solcher Verweis hat dieselbe Bedeutung wie die `MyBase.` *Methode*.</span><span class="sxs-lookup"><span data-stu-id="243bb-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>

<span data-ttu-id="243bb-169">Im folgenden Beispiel werden `Me` und verglichen `MyClass` .</span><span class="sxs-lookup"><span data-stu-id="243bb-169">The following example compares `Me` and `MyClass`.</span></span>

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

<span data-ttu-id="243bb-170">Obwohl `derivedClass` überschreibt `testMethod` , wird durch das- `MyClass` Schlüsselwort in `useMyClass` die Auswirkungen der Überschreibung aufgehoben, und der Compiler löst den-Rückruf der Basisklassen Version von auf `testMethod` .</span><span class="sxs-lookup"><span data-stu-id="243bb-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>

## <a name="see-also"></a><span data-ttu-id="243bb-171">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="243bb-171">See also</span></span>

- [<span data-ttu-id="243bb-172">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="243bb-172">Inherits Statement</span></span>](../../../language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="243bb-173">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="243bb-173">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
