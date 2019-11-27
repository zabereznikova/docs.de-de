---
title: Deklaration von Objektvariablen
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: d1964e3768124dde1deeabfada9006ff5a59def0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351813"
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="746cd-102">Deklaration von Objektvariablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="746cd-102">Object Variable Declaration (Visual Basic)</span></span>
<span data-ttu-id="746cd-103">Sie verwenden eine normale Deklarations Anweisung, um eine Objekt Variable zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="746cd-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="746cd-104">Für den-Datentyp geben Sie entweder `Object` (d. h. den [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)) oder eine spezifischere Klasse an, aus der das Objekt erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="746cd-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="746cd-105">Das Deklarieren einer Variablen als `Object` entspricht der Deklaration als <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="746cd-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="746cd-106">Wenn Sie eine Variable mit einer bestimmten Objektklasse deklarieren, können Sie auf alle Methoden und Eigenschaften zugreifen, die von dieser Klasse verfügbar gemacht werden, und auf die Klassen, von denen Sie erbt.</span><span class="sxs-lookup"><span data-stu-id="746cd-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="746cd-107">Wenn Sie die Variable mit <xref:System.Object>deklarieren, kann Sie nur auf die Member der <xref:System.Object> Klasse zugreifen, es sei denn, Sie aktivieren `Option Strict Off`, um spätes Binden zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="746cd-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="746cd-108">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="746cd-108">Declaration Syntax</span></span>  
 <span data-ttu-id="746cd-109">Verwenden Sie die folgende Syntax, um eine Objekt Variable zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="746cd-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="746cd-110">Sie können auch [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)oder [static](../../../../visual-basic/language-reference/modifiers/static.md) in der Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="746cd-110">You can also specify [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), or [Static](../../../../visual-basic/language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="746cd-111">Die folgenden Beispiel Deklarationen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="746cd-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="746cd-112">Späte Bindung und frühe Bindung</span><span class="sxs-lookup"><span data-stu-id="746cd-112">Late Binding and Early Binding</span></span>  
 <span data-ttu-id="746cd-113">Manchmal ist die bestimmte Klasse unbekannt, bis der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="746cd-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="746cd-114">In diesem Fall müssen Sie die Objekt Variable mit dem `Object`-Datentyp deklarieren.</span><span class="sxs-lookup"><span data-stu-id="746cd-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="746cd-115">Dadurch wird ein allgemeiner Verweis auf einen beliebigen Objekttyp erstellt, und die jeweilige Klasse wird zur Laufzeit zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="746cd-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="746cd-116">Dies wird als *späte Bindung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="746cd-116">This is called *late binding*.</span></span> <span data-ttu-id="746cd-117">Die späte Bindung erfordert zusätzliche Ausführungszeit.</span><span class="sxs-lookup"><span data-stu-id="746cd-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="746cd-118">Außerdem schränkt er Ihren Code auf die Methoden und Eigenschaften der Klasse ein, die Sie zuletzt zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="746cd-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="746cd-119">Dies kann zu Laufzeitfehlern führen, wenn der Code versucht, auf Member einer anderen Klasse zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="746cd-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="746cd-120">Wenn Sie die jeweilige Klasse zum Zeitpunkt der Kompilierung kennen, sollten Sie die Objekt Variable so deklarieren, dass Sie dieser Klasse entspricht.</span><span class="sxs-lookup"><span data-stu-id="746cd-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="746cd-121">Dies wird als *frühe Bindung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="746cd-121">This is called *early binding*.</span></span> <span data-ttu-id="746cd-122">Frühe Bindungen verbessern die Leistung und gewährleisten, dass Ihr Code auf alle Methoden und Eigenschaften der jeweiligen Klasse zugreift.</span><span class="sxs-lookup"><span data-stu-id="746cd-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="746cd-123">Wenn in den vorangehenden Beispiel Deklarationen die Variable `objA` nur Objekte der Klasse <xref:System.Windows.Forms.Label?displayProperty=nameWithType>verwendet, sollten Sie `As System.Windows.Forms.Label` in der Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="746cd-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="746cd-124">Vorteile der frühen Bindung</span><span class="sxs-lookup"><span data-stu-id="746cd-124">Advantages of Early Binding</span></span>  
 <span data-ttu-id="746cd-125">Das Deklarieren einer Objektvariablen als eine bestimmte Klasse bietet mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="746cd-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
- <span data-ttu-id="746cd-126">Automatische Typüberprüfung</span><span class="sxs-lookup"><span data-stu-id="746cd-126">Automatic type checking</span></span>  
  
- <span data-ttu-id="746cd-127">Garantierte Zugriffsberechtigung für alle Member der bestimmten Klasse</span><span class="sxs-lookup"><span data-stu-id="746cd-127">Guaranteed access to all members of the specific class</span></span>  
  
- <span data-ttu-id="746cd-128">Microsoft IntelliSense-Unterstützung im Code-Editor</span><span class="sxs-lookup"><span data-stu-id="746cd-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
- <span data-ttu-id="746cd-129">Bessere Lesbarkeit des Codes</span><span class="sxs-lookup"><span data-stu-id="746cd-129">Improved readability of your code</span></span>  
  
- <span data-ttu-id="746cd-130">Weniger Fehler in Ihrem Code</span><span class="sxs-lookup"><span data-stu-id="746cd-130">Fewer errors in your code</span></span>  
  
- <span data-ttu-id="746cd-131">Fehler, die zur Kompilierzeit statt zur Laufzeit abgefangen wurden.</span><span class="sxs-lookup"><span data-stu-id="746cd-131">Errors caught at compile time rather than run time</span></span>  
  
- <span data-ttu-id="746cd-132">Schnellere Codeausführung</span><span class="sxs-lookup"><span data-stu-id="746cd-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="746cd-133">Zugriff auf Objektvariablen Elemente</span><span class="sxs-lookup"><span data-stu-id="746cd-133">Access to Object Variable Members</span></span>  
 <span data-ttu-id="746cd-134">Wenn `Option Strict` `On`aktiviert ist, kann eine Objekt Variable nur auf die Methoden und Eigenschaften der Klasse zugreifen, mit der Sie Sie deklarieren.</span><span class="sxs-lookup"><span data-stu-id="746cd-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="746cd-135">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="746cd-135">The following example illustrates this.</span></span>  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 <span data-ttu-id="746cd-136">In diesem Beispiel kann `p` nur die Mitglieder der <xref:System.Object> -Klasse selbst verwenden, die nicht die `Left` -Eigenschaft enthalten.</span><span class="sxs-lookup"><span data-stu-id="746cd-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="746cd-137">Auf der anderen Seite wurde `q` als Typ <xref:System.Windows.Forms.Label>deklariert, sodass es alle Methoden und Eigenschaften der <xref:System.Windows.Forms.Label> -Klasse im <xref:System.Windows.Forms> -Namespace verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="746cd-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="746cd-138">Flexibilität von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="746cd-138">Flexibility of Object Variables</span></span>  
 <span data-ttu-id="746cd-139">Beim Arbeiten mit Objekten in einer Vererbungs Hierarchie haben Sie die Wahl, welche Klasse zum Deklarieren der Objektvariablen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="746cd-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="746cd-140">Wenn Sie diese Auswahl treffen, müssen Sie die Flexibilität der Objekt Zuweisung gegen den Zugriff auf die Member einer Klasse ausgleichen.</span><span class="sxs-lookup"><span data-stu-id="746cd-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="746cd-141">Nehmen Sie beispielsweise die Vererbungs Hierarchie, die zur <xref:System.Windows.Forms.Form?displayProperty=nameWithType>-Klasse führt:</span><span class="sxs-lookup"><span data-stu-id="746cd-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="746cd-142">Angenommen, Ihre Anwendung definiert eine Formular Klasse mit dem Namen `specialForm`, die von Class <xref:System.Windows.Forms.Form>erbt.</span><span class="sxs-lookup"><span data-stu-id="746cd-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="746cd-143">Sie können eine Objekt Variable deklarieren, die speziell auf `specialForm`verweist, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="746cd-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="746cd-144">Die-Deklaration im vorangehenden Beispiel schränkt die Variablen `nextForm` auf Objekte der Klasse `specialForm`, aber auch alle Methoden und Eigenschaften von `specialForm` verfügbar `nextForm`sowie alle Member aller Klassen, von denen `specialForm` erbt.</span><span class="sxs-lookup"><span data-stu-id="746cd-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="746cd-145">Sie können eine Objekt Variable allgemeiner machen, indem Sie Sie als Typ <xref:System.Windows.Forms.Form>deklarieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="746cd-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="746cd-146">Mit der Deklaration im vorherigen Beispiel können Sie `anyForm`beliebige Formulare in der Anwendung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="746cd-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="746cd-147">Obwohl `anyForm` auf alle Member der Klasse <xref:System.Windows.Forms.Form>zugreifen kann, können keine zusätzlichen Methoden oder Eigenschaften verwendet werden, die für bestimmte Formulare wie `specialForm`definiert sind.</span><span class="sxs-lookup"><span data-stu-id="746cd-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="746cd-148">Alle Member einer Basisklasse sind für abgeleitete Klassen verfügbar, aber die zusätzlichen Member einer abgeleiteten Klasse sind für die Basisklasse nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="746cd-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="746cd-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="746cd-149">See also</span></span>

- [<span data-ttu-id="746cd-150">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="746cd-150">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="746cd-151">Zuweisen von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="746cd-151">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="746cd-152">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="746cd-152">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="746cd-153">Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="746cd-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="746cd-154">Gewusst wie: Zugreifen auf Member eines Objekts</span><span class="sxs-lookup"><span data-stu-id="746cd-154">How to: Access Members of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [<span data-ttu-id="746cd-155">New-Operator</span><span class="sxs-lookup"><span data-stu-id="746cd-155">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="746cd-156">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="746cd-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="746cd-157">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="746cd-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
