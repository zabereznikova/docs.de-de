---
title: 'Vorgehensweise: Eine Variable erstellen, die sich nicht im Wert ändert (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d201e95463dd0431825fee03ebfd340ac80cc552
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630884"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="da083-102">Vorgehensweise: Eine Variable erstellen, die sich nicht im Wert ändert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da083-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>

<span data-ttu-id="da083-103">Das Konzept einer Variablen, deren Wert nicht geändert wird, mag widersprüchlich erscheinen.</span><span class="sxs-lookup"><span data-stu-id="da083-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="da083-104">Es gibt jedoch Situationen, in denen eine Konstante nicht realisierbar ist, und es sinnvoll ist, eine Variable mit einem Fixed-Wert zu haben.</span><span class="sxs-lookup"><span data-stu-id="da083-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="da083-105">In einem solchen Fall können Sie eine Member-Variable [mit dem Schlüssel](../../../../visual-basic/language-reference/modifiers/readonly.md) Wort "schreibgeschützt" definieren.</span><span class="sxs-lookup"><span data-stu-id="da083-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>

<span data-ttu-id="da083-106">In den folgenden Situationen können Sie die Konstante [Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md) nicht verwenden, um einen konstanten Wert zu deklarieren und zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="da083-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>

- <span data-ttu-id="da083-107">Die `Const` Anweisung akzeptiert nicht den Datentyp, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="da083-107">The `Const` statement does not accept the data type you want to use</span></span>

- <span data-ttu-id="da083-108">Der Wert ist zur Kompilierzeit nicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="da083-108">You do not know the value at compile time</span></span>

- <span data-ttu-id="da083-109">Der Konstante Wert kann zur Kompilierzeit nicht berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="da083-109">You are unable to compute the constant value at compile time</span></span>

### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="da083-110">So erstellen Sie eine Variable, die den Wert nicht ändert</span><span class="sxs-lookup"><span data-stu-id="da083-110">To create a variable that does not change in value</span></span>

1. <span data-ttu-id="da083-111">Deklarieren Sie auf Modulebene eine Member-Variable mit der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md), und schließen Sie [das Schlüsselwort](../../../../visual-basic/language-reference/modifiers/readonly.md) "schreibgeschützt" ein.</span><span class="sxs-lookup"><span data-stu-id="da083-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>

    ```vb
    Dim ReadOnly timeStarted
    ```

    <span data-ttu-id="da083-112">Sie können nur `ReadOnly` für eine Element Variable angeben.</span><span class="sxs-lookup"><span data-stu-id="da083-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="da083-113">Dies bedeutet, dass Sie die Variable auf Modulebene außerhalb der Prozeduren definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="da083-113">This means you must define the variable at module level, outside of any procedure.</span></span>

2. <span data-ttu-id="da083-114">Wenn Sie den Wert in einer einzelnen Anweisung zur Kompilierzeit berechnen können, verwenden Sie eine Initialisierungs Klausel in `Dim` der-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="da083-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="da083-115">Befolgen Sie die [As](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel mit einem Gleichheitszeichen (`=`), gefolgt von einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="da083-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="da083-116">Stellen Sie sicher, dass der Compiler diesen Ausdruck mit einem konstanten Wert auswerten kann.</span><span class="sxs-lookup"><span data-stu-id="da083-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    <span data-ttu-id="da083-117">Sie können einer `ReadOnly` Variablen nur einmal einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="da083-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="da083-118">Nachdem Sie dies getan haben, kann kein Code mehr seinen Wert ändern.</span><span class="sxs-lookup"><span data-stu-id="da083-118">Once you do so, no code can ever change its value.</span></span>

    <span data-ttu-id="da083-119">Wenn Sie den Wert zur Kompilierzeit nicht kennen oder ihn zur Kompilierzeit nicht in einer einzelnen Anweisung berechnen können, können Sie ihn trotzdem zur Laufzeit in einem Konstruktor zuweisen.</span><span class="sxs-lookup"><span data-stu-id="da083-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="da083-120">Zu diesem Zweck müssen Sie die `ReadOnly` Variable auf Klassen-oder Struktur Ebene deklarieren.</span><span class="sxs-lookup"><span data-stu-id="da083-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="da083-121">Berechnen Sie im Konstruktor für diese Klasse oder Struktur den festgelegten Wert der Variablen, und weisen Sie ihn der Variablen zu, bevor Sie den Konstruktor zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="da083-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>

## <a name="see-also"></a><span data-ttu-id="da083-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da083-122">See also</span></span>

- [<span data-ttu-id="da083-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="da083-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="da083-124">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="da083-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
