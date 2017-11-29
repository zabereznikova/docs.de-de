---
title: Objektvariablen in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44689d649a381618e5d6c934deb2b7b9bea463ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="73515-102">Objektvariablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73515-102">Object Variables in Visual Basic</span></span>
<span data-ttu-id="73515-103">Zusätzlich zum Speichern von Werten direkt, kann eine Variable auf ein Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="73515-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="73515-104">Sie können eine Variable ein Objekt zuweisen, denselben Gründen, die Sie einen beliebigen Wert einer Variablen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="73515-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>  
  
-   <span data-ttu-id="73515-105">Ein Variablenname ist häufig kürzer und leichter merken als der vollständige Pfad der Methoden und Eigenschaften, die Zugriff auf das Objekt selbst erforderlich.</span><span class="sxs-lookup"><span data-stu-id="73515-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>  
  
-   <span data-ttu-id="73515-106">Verwenden eine Variable, die auf ein Objekt verweist, ist effizienter als wiederholt den Zugriff auf das Objekt selbst, über die erforderlichen Methoden oder Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="73515-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>  
  
-   <span data-ttu-id="73515-107">Sie können ändern, eine Variable, die auf andere Objekte verweisen, während Ihr Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="73515-107">You can change a variable to refer to other objects while your code is running.</span></span>  
  
## <a name="making-code-shorter"></a><span data-ttu-id="73515-108">Verkürzen des Codes</span><span class="sxs-lookup"><span data-stu-id="73515-108">Making Code Shorter</span></span>  
 <span data-ttu-id="73515-109">Sie können Objektvariablen verwenden, um den Code zu kürzen, den Sie eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="73515-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="73515-110">Im folgenden Beispiel wird den vollständigen Pfad der Methoden und Eigenschaften den Zugriff auf eine <xref:System.Windows.Forms.Control> Objekt.</span><span class="sxs-lookup"><span data-stu-id="73515-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 <span data-ttu-id="73515-111">Sie können diesen Code kürzen, und Sie können Ausführung beschleunigt wird, wenn Sie eine Objektvariable für das Steuerelement verwendet.</span><span class="sxs-lookup"><span data-stu-id="73515-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="73515-112">Sie sollten die Objektvariable mit der Klasse, die Sie zuweisen möchten deklarieren (`Control` in diesem Fall).</span><span class="sxs-lookup"><span data-stu-id="73515-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="73515-113">Nachdem Sie die Variable ein Objekt zuweisen, können Sie sie genauso behandeln wie das Objekt zu behandeln, auf dem verwiesen.</span><span class="sxs-lookup"><span data-stu-id="73515-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="73515-114">Festlegen oder Abrufen der Eigenschaften des Objekts, oder verwenden keine der Methoden.</span><span class="sxs-lookup"><span data-stu-id="73515-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="73515-115">Im folgenden Beispiel wird eine Objektvariable, um den Code im vorhergehenden Beispiel zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="73515-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a><span data-ttu-id="73515-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73515-116">See Also</span></span>  
 [<span data-ttu-id="73515-117">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="73515-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="73515-118">Gewusst wie: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad</span><span class="sxs-lookup"><span data-stu-id="73515-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [<span data-ttu-id="73515-119">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="73515-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="73515-120">Zuweisen von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="73515-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="73515-121">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="73515-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
