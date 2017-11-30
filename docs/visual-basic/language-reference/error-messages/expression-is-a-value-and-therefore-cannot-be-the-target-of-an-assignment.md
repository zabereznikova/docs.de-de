---
title: Der Ausdruck ist ein Wert und kann nicht als Ziel einer Zuweisung verwendet werden
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords: BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bec3e2d298160bd0b459dc3b7ef93b94648e439a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="baf8d-102">Der Ausdruck ist ein Wert und kann nicht als Ziel einer Zuweisung verwendet werden</span><span class="sxs-lookup"><span data-stu-id="baf8d-102">Expression is a value and therefore cannot be the target of an assignment</span></span>
<span data-ttu-id="baf8d-103">Eine Anweisung versucht, ein Ausdruck einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="baf8d-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="baf8d-104">Sie können einen Wert zur Laufzeit nur auf eine schreibbare Variable, eine Eigenschaft oder ein Arrayelement zuweisen.</span><span class="sxs-lookup"><span data-stu-id="baf8d-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="baf8d-105">Im folgende Beispiel wird veranschaulicht, wie dieser Fehler kann auftreten.</span><span class="sxs-lookup"><span data-stu-id="baf8d-105">The following example illustrates how this error can occur.</span></span>  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 <span data-ttu-id="baf8d-106">Ähnliche Beispiele konnte auf Eigenschaften und Elemente des Arrays angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="baf8d-106">Similar examples could apply to properties and array elements.</span></span>  
  
 <span data-ttu-id="baf8d-107">**Indirekten Zugang.**</span><span class="sxs-lookup"><span data-stu-id="baf8d-107">**Indirect Access.**</span></span> <span data-ttu-id="baf8d-108">Dieser Fehler kann auch durch Indirekter Zugriff über einen Werttyp generiert werden.</span><span class="sxs-lookup"><span data-stu-id="baf8d-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="baf8d-109">Betrachten Sie das folgende Codebeispiel, zum Festlegen des Werts der zielt <xref:System.Drawing.Point> von indirekten Zugriff über <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="baf8d-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 <span data-ttu-id="baf8d-110">Die letzte Anweisung im obigen Beispiel schlägt fehl, da dadurch entstehen, dass nur eine temporäre Zuordnung für die <xref:System.Drawing.Point> zurückgegebene Struktur der <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="baf8d-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="baf8d-111">Eine Struktur ein Werttyp ist, und die temporäre Struktur wird nicht beibehalten, nachdem die Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="baf8d-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="baf8d-112">Das Problem ist behoben, durch Deklarieren und verwenden eine Variable für <xref:System.Windows.Forms.Control.Location%2A>, wodurch erstellt eine permanente Zuordnung für die <xref:System.Drawing.Point> Struktur.</span><span class="sxs-lookup"><span data-stu-id="baf8d-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="baf8d-113">Im folgende Beispiel wird gezeigt, Code, der die letzte Anweisung im obigen Beispiel ersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="baf8d-113">The following example shows code that can replace the last statement of the preceding example.</span></span>  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 <span data-ttu-id="baf8d-114">**Fehler-ID:** BC30068</span><span class="sxs-lookup"><span data-stu-id="baf8d-114">**Error ID:** BC30068</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="baf8d-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="baf8d-115">To correct this error</span></span>  
  
-   <span data-ttu-id="baf8d-116">Wenn die Anweisung ein Ausdruck einen Wert zuweist, ersetzen Sie den Ausdruck durch eine einzelne schreibbare Variable, eine Eigenschaft oder ein Arrayelement.</span><span class="sxs-lookup"><span data-stu-id="baf8d-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>  
  
-   <span data-ttu-id="baf8d-117">Wenn die Anweisung indirekten Zugriff über einen Werttyp (in der Regel eine Struktur) herstellt, erstellen Sie eine Variable, um den Werttyp.</span><span class="sxs-lookup"><span data-stu-id="baf8d-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>  
  
-   <span data-ttu-id="baf8d-118">Weisen Sie die entsprechende Struktur (oder anderen Werttyp) der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="baf8d-118">Assign the appropriate structure (or other value type) to the variable.</span></span>  
  
-   <span data-ttu-id="baf8d-119">Verwenden Sie die Variable, um Zugriff auf die Eigenschaft, um einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="baf8d-119">Use the variable to access the property to assign it a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf8d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="baf8d-120">See Also</span></span>  
 [<span data-ttu-id="baf8d-121">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="baf8d-121">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="baf8d-122">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="baf8d-122">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="baf8d-123">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="baf8d-123">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
