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
ms.openlocfilehash: 89fcf2a14d8938d536aa72628218242811baa1a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401460"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="66d23-102">Grundlagen der Vererbung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66d23-102">Inheritance Basics (Visual Basic)</span></span>

<span data-ttu-id="66d23-103">Die `Inherits` Anweisung wird verwendet, um eine neue Klasse zu deklarieren, die als *abgeleitete Klasse*bezeichnet wird, basierend auf einer vorhandenen Klasse, die als *Basisklasse*bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="66d23-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="66d23-104">Abgeleitete Klassen erben und können die Eigenschaften, Methoden, Ereignisse, Felder und Konstanten erweitern, die in der Basisklasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="66d23-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="66d23-105">Im folgenden Abschnitt werden einige der Regeln für die Vererbung und die Modifikatoren beschrieben, mit denen Sie die Art und Weise ändern können, wie Klassen erben oder vererbt werden:</span><span class="sxs-lookup"><span data-stu-id="66d23-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>

- <span data-ttu-id="66d23-106">Standardmäßig sind alle Klassen vererbbar, `NotInheritable` es sei denn, sie werden mit dem Schlüsselwort markiert.</span><span class="sxs-lookup"><span data-stu-id="66d23-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="66d23-107">Klassen können von anderen Klassen in Ihrem Projekt oder von Klassen in anderen Assemblys erben, auf die das Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="66d23-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>

- <span data-ttu-id="66d23-108">Im Gegensatz zu Sprachen, die eine mehrfache Vererbung ermöglichen, lässt Visual Basic nur eine einzelne Vererbung in Klassen zu. Das heißt, abgeleitete Klassen können nur eine Basisklasse haben.</span><span class="sxs-lookup"><span data-stu-id="66d23-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="66d23-109">Obwohl mehrere Vererbungen in Klassen nicht zulässig sind, können Klassen mehrere Schnittstellen implementieren, wodurch die gleichen Ziele effektiv erreicht werden können.</span><span class="sxs-lookup"><span data-stu-id="66d23-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>

- <span data-ttu-id="66d23-110">Um zu verhindern, dass eingeschränkte Elemente in einer Basisklasse angezeigt werden, muss der Zugriffstyp einer abgeleiteten Klasse gleich oder restriktiver sein als die Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="66d23-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="66d23-111">Beispielsweise kann `Public` eine Klasse keine `Friend` oder `Private` eine Klasse `Friend` erben, und eine `Private` Klasse kann keine Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="66d23-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>

## <a name="inheritance-modifiers"></a><span data-ttu-id="66d23-112">Vererbungsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="66d23-112">Inheritance Modifiers</span></span>

<span data-ttu-id="66d23-113">Visual Basic führt die folgenden Anweisungen und Modifikatoren auf Klassenebene ein, um die Vererbung zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="66d23-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>

- <span data-ttu-id="66d23-114">`Inherits`anweisung – Gibt die Basisklasse an.</span><span class="sxs-lookup"><span data-stu-id="66d23-114">`Inherits` statement — Specifies the base class.</span></span>

- <span data-ttu-id="66d23-115">`NotInheritable`modifier – Verhindert, dass Programmierer die Klasse als Basisklasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="66d23-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>

- <span data-ttu-id="66d23-116">`MustInherit`modifier – Gibt an, dass die Klasse nur für die Verwendung als Basisklasse vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="66d23-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="66d23-117">Instanzen `MustInherit` von Klassen können nicht direkt erstellt werden. Sie können nur als Basisklasseninstanzen einer abgeleiteten Klasse erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="66d23-118">(Andere Programmiersprachen, wie z. B. C++ und C, verwenden den Begriff *abstrakte Klasse,* um eine solche Klasse zu beschreiben.)</span><span class="sxs-lookup"><span data-stu-id="66d23-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>

## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="66d23-119">Überschreiben von Eigenschaften und Methoden in abgeleiteten Klassen</span><span class="sxs-lookup"><span data-stu-id="66d23-119">Overriding Properties and Methods in Derived Classes</span></span>

<span data-ttu-id="66d23-120">Standardmäßig erbt eine abgeleitete Klasse Eigenschaften und Methoden von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="66d23-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="66d23-121">Wenn sich eine geerbte Eigenschaft oder Methode in der abgeleiteten Klasse anders verhalten muss, kann sie *überschrieben*werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="66d23-122">Das heißt, Sie können eine neue Implementierung der Methode in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="66d23-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="66d23-123">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="66d23-123">The following modifiers are used to control how properties and methods are overridden:</span></span>

- <span data-ttu-id="66d23-124">`Overridable`– Ermöglicht das Übersteuern einer Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="66d23-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>

- <span data-ttu-id="66d23-125">`Overrides`– Überschreibt `Overridable` eine Eigenschaft oder Methode, die in der Basisklasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="66d23-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>

- <span data-ttu-id="66d23-126">`NotOverridable`– Verhindert, dass eine Eigenschaft oder Methode in einer erbenden Klasse überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="66d23-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="66d23-127">Standardmäßig sind `Public` `NotOverridable`Methoden .</span><span class="sxs-lookup"><span data-stu-id="66d23-127">By default, `Public` methods are `NotOverridable`.</span></span>

- <span data-ttu-id="66d23-128">`MustOverride`– Erfordert, dass eine abgeleitete Klasse die Eigenschaft oder Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="66d23-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="66d23-129">Wenn `MustOverride` das Schlüsselwort verwendet wird, besteht `Sub` `Function`die `Property` Methodendefinition nur aus der , oder Anweisung.</span><span class="sxs-lookup"><span data-stu-id="66d23-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="66d23-130">Es sind keine anderen Aussagen zulässig, und insbesondere gibt es keine `End Sub` oder `End Function` Keine Aussage.</span><span class="sxs-lookup"><span data-stu-id="66d23-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="66d23-131">`MustOverride`Methoden müssen in `MustInherit` Klassen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>

<span data-ttu-id="66d23-132">Angenommen, Sie möchten Klassen definieren, um die Lohnabrechnung zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="66d23-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="66d23-133">Sie können eine `Payroll` generische Klasse `RunPayroll` definieren, die eine Methode enthält, die die Lohnabrechnung für eine typische Woche berechnet.</span><span class="sxs-lookup"><span data-stu-id="66d23-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="66d23-134">Sie können `Payroll` dann als Basisklasse für `BonusPayroll` eine spezialisiertere Klasse verwendet werden, die bei der Verteilung von Mitarbeiterboni verwendet werden könnte.</span><span class="sxs-lookup"><span data-stu-id="66d23-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>

<span data-ttu-id="66d23-135">Die `BonusPayroll` Klasse kann die in der `PayEmployee` Basisklasse `Payroll` definierte Methode erben und überschreiben.</span><span class="sxs-lookup"><span data-stu-id="66d23-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>

<span data-ttu-id="66d23-136">Im folgenden Beispiel werden eine `Payroll,` Basisklasse und `BonusPayroll`eine abgeleitete Klasse definiert, die eine geerbte Methode `PayEmployee`überschreibt.</span><span class="sxs-lookup"><span data-stu-id="66d23-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="66d23-137">Eine `RunPayroll`Prozedur, , erstellt `Payroll` und übergibt dann ein Objekt und ein `BonusPayroll` Objekt an eine Funktion, `Pay`die die `PayEmployee` Methode beider Objekte ausführt.</span><span class="sxs-lookup"><span data-stu-id="66d23-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a><span data-ttu-id="66d23-138">Das MyBase-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="66d23-138">The MyBase Keyword</span></span>

<span data-ttu-id="66d23-139">Das `MyBase` Schlüsselwort verhält sich wie eine Objektvariable, die auf die Basisklasse der aktuellen Instanz einer Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="66d23-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="66d23-140">`MyBase`wird häufig für den Zugriff auf Basisklassenmember verwendet, die in einer abgeleiteten Klasse überschrieben oder überschattet werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="66d23-141">Insbesondere wird `MyBase.New` verwendet, um explizit einen Basisklassenkonstruktor von einem abgeleiteten Klassenkonstruktor aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="66d23-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>

<span data-ttu-id="66d23-142">Angenommen, Sie entwerfen eine abgeleitete Klasse, die eine von der Basisklasse geerbte Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="66d23-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="66d23-143">Die überschriebene Methode kann die Methode in der Basisklasse aufrufen und den Rückgabewert ändern, wie im folgenden Codefragment gezeigt:</span><span class="sxs-lookup"><span data-stu-id="66d23-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

<span data-ttu-id="66d23-144">In der folgenden Liste `MyBase`werden Einschränkungen bei der Verwendung beschrieben:</span><span class="sxs-lookup"><span data-stu-id="66d23-144">The following list describes restrictions on using `MyBase`:</span></span>

- <span data-ttu-id="66d23-145">`MyBase`bezieht sich auf die unmittelbare Basisklasse und ihre geerbten Member.</span><span class="sxs-lookup"><span data-stu-id="66d23-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="66d23-146">Sie kann nicht `Private` für den Zugriff auf Member in der Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-146">It cannot be used to access `Private` members in the class.</span></span>

- <span data-ttu-id="66d23-147">`MyBase`ist ein Schlüsselwort, kein echtes Objekt.</span><span class="sxs-lookup"><span data-stu-id="66d23-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="66d23-148">`MyBase`kann nicht einer Variablen zugewiesen, an Prozeduren `Is` übergeben oder in einem Vergleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="66d23-149">Die methode, die qualifiziert ist, `MyBase` muss nicht in der unmittelbaren Basisklasse definiert werden. Sie kann stattdessen in einer indirekt geerbten Basisklasse definiert werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="66d23-150">Damit ein Verweis, `MyBase` der durch die korrekte Kompilierung qualifiziert ist, qualifiziert ist, muss eine Basisklasse eine Methode enthalten, die dem Namen und den Typen von Parametern entspricht, die im Aufruf angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>

- <span data-ttu-id="66d23-151">Sie können `MyBase` keine `MustOverride` Basisklassenmethoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="66d23-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>

- <span data-ttu-id="66d23-152">`MyBase`kann nicht verwendet werden, um sich zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="66d23-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="66d23-153">Daher ist der folgende Code ungültig:</span><span class="sxs-lookup"><span data-stu-id="66d23-153">Therefore, the following code is not valid:</span></span>

  `MyBase.MyBase.BtnOK_Click()`

- <span data-ttu-id="66d23-154">`MyBase`kann nicht in Modulen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-154">`MyBase` cannot be used in modules.</span></span>

- <span data-ttu-id="66d23-155">`MyBase`kann nicht für den Zugriff auf `Friend` Basisklassenmember verwendet werden, die so gekennzeichnet sind, als ob sich die Basisklasse in einer anderen Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="66d23-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>

<span data-ttu-id="66d23-156">Weitere Informationen und ein weiteres Beispiel finden Sie unter [Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird.](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)</span><span class="sxs-lookup"><span data-stu-id="66d23-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>

## <a name="the-myclass-keyword"></a><span data-ttu-id="66d23-157">Das MyClass-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="66d23-157">The MyClass Keyword</span></span>

<span data-ttu-id="66d23-158">Das `MyClass` Schlüsselwort verhält sich wie eine Objektvariable, die auf die aktuelle Instanz einer Klasse verweist, wie sie ursprünglich implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="66d23-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="66d23-159">`MyClass`ähnelt `Me`, aber jede Methode `MyClass` und jeder Eigenschaftsaufruf wird so behandelt, als ob die Methode oder Eigenschaft [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)wäre.</span><span class="sxs-lookup"><span data-stu-id="66d23-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="66d23-160">Daher wird die Methode oder Eigenschaft nicht durch Das Überschreiben in einer abgeleiteten Klasse beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="66d23-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>

- <span data-ttu-id="66d23-161">`MyClass`ist ein Schlüsselwort, kein echtes Objekt.</span><span class="sxs-lookup"><span data-stu-id="66d23-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="66d23-162">`MyClass`kann nicht einer Variablen zugewiesen, an Prozeduren `Is` übergeben oder in einem Vergleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="66d23-163">`MyClass`bezieht sich auf die enthaltende Klasse und ihre geerbten Member.</span><span class="sxs-lookup"><span data-stu-id="66d23-163">`MyClass` refers to the containing class and its inherited members.</span></span>

- <span data-ttu-id="66d23-164">`MyClass`kann als Qualifizierer für `Shared` Mitglieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>

- <span data-ttu-id="66d23-165">`MyClass`kann nicht innerhalb `Shared` einer Methode verwendet werden, sondern kann innerhalb einer Instanzmethode verwendet werden, um auf einen freigegebenen Member einer Klasse zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="66d23-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>

- <span data-ttu-id="66d23-166">`MyClass`kann nicht in Standardmodulen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66d23-166">`MyClass` cannot be used in standard modules.</span></span>

- <span data-ttu-id="66d23-167">`MyClass`kann verwendet werden, um eine Methode zu qualifizieren, die in einer Basisklasse definiert ist und die keine Implementierung der in dieser Klasse bereitgestellten Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="66d23-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="66d23-168">Ein solcher Verweis hat `MyBase.`die gleiche Bedeutung wie *Methode*.</span><span class="sxs-lookup"><span data-stu-id="66d23-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>

<span data-ttu-id="66d23-169">Im folgenden Beispiel `Me` `MyClass`werden vergleicht und .</span><span class="sxs-lookup"><span data-stu-id="66d23-169">The following example compares `Me` and `MyClass`.</span></span>

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

<span data-ttu-id="66d23-170">Obwohl `derivedClass` überschrieben `testMethod`wird, hebt das `MyClass` Schlüsselwort in `useMyClass` die Auswirkungen des Überschreibens auf, `testMethod`und der Compiler löst den Aufruf der Basisklassenversion von auf.</span><span class="sxs-lookup"><span data-stu-id="66d23-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>

## <a name="see-also"></a><span data-ttu-id="66d23-171">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66d23-171">See also</span></span>

- [<span data-ttu-id="66d23-172">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="66d23-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="66d23-173">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="66d23-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
