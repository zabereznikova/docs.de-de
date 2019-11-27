---
title: Objektvariablen
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 7eb860bc732f923316b8ce1d7b94ecdb368bfec3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351780"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="cf8ad-102">Objektvariablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf8ad-102">Object Variables in Visual Basic</span></span>

<span data-ttu-id="cf8ad-103">Neben der direkten Speicherung von Werten kann eine Variable auf ein Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="cf8ad-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="cf8ad-104">Sie weisen einer Variablen ein Objekt zu, wenn Sie einer Variablen einen beliebigen Wert zuweisen:</span><span class="sxs-lookup"><span data-stu-id="cf8ad-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>

- <span data-ttu-id="cf8ad-105">Ein Variablenname ist oft kürzer und leichter zu merken als der vollständige Pfad von Methoden und Eigenschaften, die für den Zugriff auf das Objekt selbst erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cf8ad-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>

- <span data-ttu-id="cf8ad-106">Die Verwendung einer Variablen, die auf ein Objekt verweist, ist effizienter als das wiederholte zugreifen auf das Objekt selbst über die erforderlichen Methoden oder Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="cf8ad-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>

- <span data-ttu-id="cf8ad-107">Sie können eine Variable ändern, um auf andere Objekte zu verweisen, während der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cf8ad-107">You can change a variable to refer to other objects while your code is running.</span></span>

## <a name="making-code-shorter"></a><span data-ttu-id="cf8ad-108">Code kürzerer Code</span><span class="sxs-lookup"><span data-stu-id="cf8ad-108">Making Code Shorter</span></span>

<span data-ttu-id="cf8ad-109">Sie können Objektvariablen verwenden, um den Code zu kürzen, den Sie eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="cf8ad-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="cf8ad-110">Im folgenden Beispiel wird der vollständige Pfad von Methoden und Eigenschaften für den Zugriff auf ein <xref:System.Windows.Forms.Control> Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf8ad-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

<span data-ttu-id="cf8ad-111">Sie können diesen Code verkürzen und die Ausführung beschleunigen, wenn Sie eine Objekt Variable für das Steuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf8ad-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="cf8ad-112">Sie sollten die Objekt Variable mit der bestimmten Klasse deklarieren, die Sie Ihr zuweisen möchten (in diesem Fall`Control`).</span><span class="sxs-lookup"><span data-stu-id="cf8ad-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="cf8ad-113">Nachdem Sie der Variablen ein Objekt zugewiesen haben, können Sie es genauso behandeln wie das Objekt, auf das es verweist.</span><span class="sxs-lookup"><span data-stu-id="cf8ad-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="cf8ad-114">Sie können die Eigenschaften des Objekts festlegen oder Abrufen oder eine der zugehörigen Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf8ad-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="cf8ad-115">Im folgenden Beispiel wird eine Objekt Variable verwendet, um den Code im vorherigen Beispiel zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="cf8ad-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a><span data-ttu-id="cf8ad-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf8ad-116">See also</span></span>

- [<span data-ttu-id="cf8ad-117">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="cf8ad-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="cf8ad-118">Gewusst wie: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad</span><span class="sxs-lookup"><span data-stu-id="cf8ad-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="cf8ad-119">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="cf8ad-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="cf8ad-120">Zuweisen von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="cf8ad-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="cf8ad-121">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="cf8ad-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
