---
title: Objektvariablen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: cc5be13293a89e73d1790e94a99d7936f1711e12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961233"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="17408-102">Objektvariablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17408-102">Object Variables in Visual Basic</span></span>

<span data-ttu-id="17408-103">Zusätzlich zum Speichern von Werten direkt aus, kann eine Variable auf ein Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="17408-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="17408-104">Sie können ein Objekt einer Variablen zuweisen, aus denselben Gründen, die Sie einen beliebigen Wert einer Variablen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="17408-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>

- <span data-ttu-id="17408-105">Ein Variablenname ist oftmals kürzer und leichter merken als den vollständigen Pfad der Methoden und Eigenschaften, die zum Zugriff auf das Objekt selbst.</span><span class="sxs-lookup"><span data-stu-id="17408-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>

- <span data-ttu-id="17408-106">Verwenden eine Variable, die auf ein Objekt verweist, ist effizienter als die wiederholt den Zugriff auf das Objekt selbst, über die erforderlichen Methoden oder Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="17408-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>

- <span data-ttu-id="17408-107">Sie können ändern, dass eine Variable, die auf andere Objekte verweisen, während Ihr Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="17408-107">You can change a variable to refer to other objects while your code is running.</span></span>

## <a name="making-code-shorter"></a><span data-ttu-id="17408-108">Verkürzen des Codes</span><span class="sxs-lookup"><span data-stu-id="17408-108">Making Code Shorter</span></span>

<span data-ttu-id="17408-109">Sie können Objektvariablen verwenden, um den Code zu verkürzen, den Sie eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="17408-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="17408-110">Im folgenden Beispiel wird den vollständigen Pfad der Methoden und Eigenschaften den Zugriff auf eine <xref:System.Windows.Forms.Control> Objekt.</span><span class="sxs-lookup"><span data-stu-id="17408-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

<span data-ttu-id="17408-111">Sie können diesen Code zu verkürzen und Ausführung beschleunigt wird, wenn Sie eine Objektvariablen für das Steuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="17408-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="17408-112">Sie sollten deklarieren und mit der Klasse, die Sie zuweisen möchten (`Control` in diesem Fall).</span><span class="sxs-lookup"><span data-stu-id="17408-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="17408-113">Nachdem Sie ein Objekt der Variablen zugewiesen haben, können Sie es genauso behandeln wie behandeln Sie das Objekt auf den er verweist.</span><span class="sxs-lookup"><span data-stu-id="17408-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="17408-114">Sie können festlegen oder Abrufen der Eigenschaften des Objekts oder keine ihrer Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="17408-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="17408-115">Im folgenden Beispiel wird eine Objektvariable, um den Code im vorherigen Beispiel zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="17408-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a><span data-ttu-id="17408-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17408-116">See also</span></span>

- [<span data-ttu-id="17408-117">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="17408-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="17408-118">Vorgehensweise: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad</span><span class="sxs-lookup"><span data-stu-id="17408-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="17408-119">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="17408-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="17408-120">Zuweisen von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="17408-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="17408-121">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="17408-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
