---
title: Der Ausdruck ist ein Wert und kann nicht als Ziel einer Zuweisung verwendet werden
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 3027be6ee4ed3664b81c661b6a086a3604573833
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802608"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="74bc0-102">Der Ausdruck ist ein Wert und kann nicht als Ziel einer Zuweisung verwendet werden</span><span class="sxs-lookup"><span data-stu-id="74bc0-102">Expression is a value and therefore cannot be the target of an assignment</span></span>
<span data-ttu-id="74bc0-103">Eine Anweisung versucht, ein Ausdruck einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="74bc0-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="74bc0-104">Sie können einen Wert nur auf eine schreibbare Variable, eine Eigenschaft oder ein Arrayelement zur Laufzeit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="74bc0-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="74bc0-105">Im folgende Beispiel wird veranschaulicht, wie dieser Fehler kann auftreten.</span><span class="sxs-lookup"><span data-stu-id="74bc0-105">The following example illustrates how this error can occur.</span></span>  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 <span data-ttu-id="74bc0-106">Ähnliche Beispiele können auf Eigenschaften und Elemente des Arrays anwenden.</span><span class="sxs-lookup"><span data-stu-id="74bc0-106">Similar examples could apply to properties and array elements.</span></span>  
  
 <span data-ttu-id="74bc0-107">**Indirekten Zugriff.**</span><span class="sxs-lookup"><span data-stu-id="74bc0-107">**Indirect Access.**</span></span> <span data-ttu-id="74bc0-108">Dieser Fehler kann auch von Indirekter Zugriff über einen Werttyp generiert werden.</span><span class="sxs-lookup"><span data-stu-id="74bc0-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="74bc0-109">Beachten Sie im folgenden Codebeispiel wird, der versucht, den Wert festlegen <xref:System.Drawing.Point> von indirekten Zugriff über <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="74bc0-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 <span data-ttu-id="74bc0-110">Die letzte Anweisung im obigen Beispiel schlägt fehl, da nur eine temporäre Zuordnung für erstellt die <xref:System.Drawing.Point> vom zurückgegebene Struktur der <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="74bc0-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="74bc0-111">Eine Struktur ein Werttyp ist, und die temporäre Struktur wird nicht beibehalten, nachdem die Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="74bc0-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="74bc0-112">Das Problem ist behoben, durch Deklarieren und verwenden eine Variable für <xref:System.Windows.Forms.Control.Location%2A>, erstellt eine permanente Zuordnung für die <xref:System.Drawing.Point> Struktur.</span><span class="sxs-lookup"><span data-stu-id="74bc0-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="74bc0-113">Das folgende Beispiel zeigt Code, der die letzte Anweisung der im vorherigen Beispiel ersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="74bc0-113">The following example shows code that can replace the last statement of the preceding example.</span></span>  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 <span data-ttu-id="74bc0-114">**Fehler-ID:** BC30068</span><span class="sxs-lookup"><span data-stu-id="74bc0-114">**Error ID:** BC30068</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="74bc0-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="74bc0-115">To correct this error</span></span>  
  
- <span data-ttu-id="74bc0-116">Wenn die Anweisung ein Ausdruck einen Wert zuweist, ersetzen Sie den Ausdruck durch eine einzelne schreibbare Variable, eine Eigenschaft oder ein Arrayelement aus.</span><span class="sxs-lookup"><span data-stu-id="74bc0-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>  
  
- <span data-ttu-id="74bc0-117">Wenn die Anweisung indirekten Zugriff über einen Werttyp (in der Regel eine Struktur) ist, erstellen Sie eine Variable für den Werttyp.</span><span class="sxs-lookup"><span data-stu-id="74bc0-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>  
  
- <span data-ttu-id="74bc0-118">Weisen Sie die entsprechende Struktur (oder anderen Werttyp) auf die Variable an.</span><span class="sxs-lookup"><span data-stu-id="74bc0-118">Assign the appropriate structure (or other value type) to the variable.</span></span>  
  
- <span data-ttu-id="74bc0-119">Verwenden Sie die Variable, um Zugriff auf die Eigenschaft es sich um einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="74bc0-119">Use the variable to access the property to assign it a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74bc0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74bc0-120">See also</span></span>

- [<span data-ttu-id="74bc0-121">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="74bc0-121">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="74bc0-122">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="74bc0-122">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="74bc0-123">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="74bc0-123">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
