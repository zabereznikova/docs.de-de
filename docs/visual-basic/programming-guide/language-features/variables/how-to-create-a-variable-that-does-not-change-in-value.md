---
title: 'Gewusst wie: Erstellen einer Variablen mit unveränderlichem Wert (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d63c254abe6d12c094e0d1252c9721f668947f09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651375"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="b5db8-102">Gewusst wie: Erstellen einer Variablen mit unveränderlichem Wert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5db8-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>
<span data-ttu-id="b5db8-103">Das Konzept einer Variablen, die nicht mit seinen Wert ändert möglicherweise widersprüchlich werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5db8-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="b5db8-104">Aber es gibt Situationen, wenn eine Konstante nicht möglich ist, und es ist sinnvoll, eine Variable mit einem festen Wert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b5db8-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="b5db8-105">In diesem Fall definieren Sie eine Membervariable mit dem [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b5db8-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
 <span data-ttu-id="b5db8-106">Sie können keine der [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md) zu deklarieren und Zuweisen eines konstanten Werts in den folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="b5db8-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>  
  
-   <span data-ttu-id="b5db8-107">Die `Const` Anweisung nimmt nicht an den Datentyp, die Sie verwenden möchten</span><span class="sxs-lookup"><span data-stu-id="b5db8-107">The `Const` statement does not accept the data type you want to use</span></span>  
  
-   <span data-ttu-id="b5db8-108">Sie den Wert zum Zeitpunkt der Kompilierung nicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="b5db8-108">You do not know the value at compile time</span></span>  
  
-   <span data-ttu-id="b5db8-109">Sie sind nicht zum Zeitpunkt der Kompilierung den konstanten Wert zu berechnen</span><span class="sxs-lookup"><span data-stu-id="b5db8-109">You are unable to compute the constant value at compile time</span></span>  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="b5db8-110">So erstellen eine Variable, die nicht geändert wird, Wert</span><span class="sxs-lookup"><span data-stu-id="b5db8-110">To create a variable that does not change in value</span></span>  
  
1.  <span data-ttu-id="b5db8-111">Auf Modulebene, deklarieren Sie eine Membervariable mit dem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md), und enthalten die [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b5db8-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     <span data-ttu-id="b5db8-112">Sie können angeben, `ReadOnly` nur in einer Membervariablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b5db8-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="b5db8-113">Dies bedeutet, dass Sie die Variable auf Modulebene außerhalb einer Prozedur definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="b5db8-113">This means you must define the variable at module level, outside of any procedure.</span></span>  
  
2.  <span data-ttu-id="b5db8-114">Wenn Sie den Wert in einer einzelnen Anweisung zum Zeitpunkt der Kompilierung berechnen können, verwenden Sie eine Initialisierungsklausel in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b5db8-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="b5db8-115">Führen Sie die [als](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel mit einem Gleichheitszeichen (`=`), gefolgt von einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b5db8-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="b5db8-116">Achten Sie darauf, dass der Compiler diesen Ausdruck mit einem konstanten Wert ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b5db8-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     <span data-ttu-id="b5db8-117">Sie können einen Wert zuweisen einer `ReadOnly` Variable nur einmal.</span><span class="sxs-lookup"><span data-stu-id="b5db8-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="b5db8-118">Sobald dies geschehen ist, kann kein Code sein Wert jemals ändern.</span><span class="sxs-lookup"><span data-stu-id="b5db8-118">Once you do so, no code can ever change its value.</span></span>  
  
     <span data-ttu-id="b5db8-119">Wenn Sie den Wert zum Zeitpunkt der Kompilierung nicht bekannt, oder können nicht zum Zeitpunkt der Kompilierung in einer einzelnen Anweisung berechnet, können Sie immer noch zur Laufzeit in einem Konstruktor zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b5db8-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="b5db8-120">Zu diesem Zweck müssen Sie deklarieren die `ReadOnly` Variable Ebene der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="b5db8-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="b5db8-121">Berechnen Sie im Konstruktor für diese Klasse oder Struktur die Variable festen Wert zu, und weisen sie der Variablen vor der Rückgabe aus dem Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="b5db8-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5db8-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5db8-122">See Also</span></span>  
 [<span data-ttu-id="b5db8-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="b5db8-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [<span data-ttu-id="b5db8-124">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b5db8-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
