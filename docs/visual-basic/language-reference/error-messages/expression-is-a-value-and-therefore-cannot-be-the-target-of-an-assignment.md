---
title: Der Ausdruck ist ein Wert und kann nicht als Ziel einer Zuweisung verwendet werden
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: cd23e6c2beb2f93578a350bc41a780c9ab785f26
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160892"
---
# <a name="bc30068-expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="2c3c2-102">BC30068: der Ausdruck ist ein Wert und kann daher nicht das Ziel einer Zuweisung sein.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-102">BC30068: Expression is a value and therefore cannot be the target of an assignment</span></span>

<span data-ttu-id="2c3c2-103">Eine Anweisung versucht, einem Ausdruck einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="2c3c2-104">Sie können einen Wert nur einer beschreibbaren Variablen, einer Eigenschaft oder einem Array Element zur Laufzeit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="2c3c2-105">Im folgenden Beispiel wird veranschaulicht, wie dieser Fehler auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-105">The following example illustrates how this error can occur.</span></span>

```vb
Dim yesterday As Integer
ReadOnly maximum As Integer = 45
yesterday + 1 = DatePart(DateInterval.Day, Now)
' The preceding line is an ERROR because of an expression on the left.
maximum = 50
' The preceding line is an ERROR because maximum is declared ReadOnly.
```

<span data-ttu-id="2c3c2-106">Ähnliche Beispiele können auf Eigenschaften und Array Elemente angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-106">Similar examples could apply to properties and array elements.</span></span>

<span data-ttu-id="2c3c2-107">**Indirekter Zugriff.**</span><span class="sxs-lookup"><span data-stu-id="2c3c2-107">**Indirect Access.**</span></span> <span data-ttu-id="2c3c2-108">Dieser Fehler kann auch durch indirekten Zugriff durch einen Werttyp generiert werden.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="2c3c2-109">Sehen Sie sich das folgende Codebeispiel an, das versucht, den Wert von festzulegen, <xref:System.Drawing.Point> indem Sie indirekt über darauf zugreifen <xref:System.Windows.Forms.Control.Location%2A> .</span><span class="sxs-lookup"><span data-stu-id="2c3c2-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

<span data-ttu-id="2c3c2-110">Die letzte Anweisung des vorangehenden Beispiels schlägt fehl, da Sie nur eine temporäre Zuordnung für die-Struktur erstellt, die <xref:System.Drawing.Point> von der-Eigenschaft zurückgegeben wird <xref:System.Windows.Forms.Control.Location%2A> .</span><span class="sxs-lookup"><span data-stu-id="2c3c2-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="2c3c2-111">Eine Struktur ist ein Werttyp, und die temporäre Struktur wird nicht beibehalten, nachdem die Anweisung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="2c3c2-112">Das Problem wird durch Deklarieren und Verwenden einer Variablen für gelöst <xref:System.Windows.Forms.Control.Location%2A> , wodurch eine permanente Zuordnung für die Struktur erstellt wird <xref:System.Drawing.Point> .</span><span class="sxs-lookup"><span data-stu-id="2c3c2-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="2c3c2-113">Das folgende Beispiel zeigt Code, der die letzte-Anweisung des vorangehenden Beispiels ersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-113">The following example shows code that can replace the last statement of the preceding example.</span></span>

```vb
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)
exitButton.Location = exitLocation
```

<span data-ttu-id="2c3c2-114">**Fehler-ID:** BC30068</span><span class="sxs-lookup"><span data-stu-id="2c3c2-114">**Error ID:** BC30068</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="2c3c2-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="2c3c2-115">To correct this error</span></span>

- <span data-ttu-id="2c3c2-116">Wenn die Anweisung einem Ausdruck einen Wert zuweist, ersetzen Sie den Ausdruck durch eine einzelne beschreibbare Variable, eine Eigenschaft oder ein Array Element.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>

- <span data-ttu-id="2c3c2-117">Wenn die Anweisung indirekten Zugriff über einen Werttyp (in der Regel eine Struktur) gewährt, erstellen Sie eine Variable, die den Werttyp enthält.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>

- <span data-ttu-id="2c3c2-118">Weisen Sie der Variablen die entsprechende Struktur (oder einen anderen Werttyp) zu.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-118">Assign the appropriate structure (or other value type) to the variable.</span></span>

- <span data-ttu-id="2c3c2-119">Verwenden Sie die-Variable, um auf die-Eigenschaft zuzugreifen, um ihr einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="2c3c2-119">Use the variable to access the property to assign it a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c3c2-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c3c2-120">See also</span></span>

- [<span data-ttu-id="2c3c2-121">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="2c3c2-121">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="2c3c2-122">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="2c3c2-122">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="2c3c2-123">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="2c3c2-123">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
