---
title: 'Vorgehensweise: Erstellen einer Variablen mit unveränderlichem Wert'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 04e08784b5cfbdeb6db73b9b00fe9afa201bd06d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410515"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="8f5ec-102">Gewusst wie: Erstellen einer Variablen mit unveränderlichem Wert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f5ec-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>

<span data-ttu-id="8f5ec-103">Das Konzept einer Variablen, deren Wert nicht geändert wird, mag widersprüchlich erscheinen.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="8f5ec-104">Es gibt jedoch Situationen, in denen eine Konstante nicht realisierbar ist, und es sinnvoll ist, eine Variable mit einem Fixed-Wert zu haben.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="8f5ec-105">In einem solchen Fall können Sie eine Member-Variable [mit dem Schlüssel](../../../language-reference/modifiers/readonly.md) Wort "schreibgeschützt" definieren.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-105">In such a case you can define a member variable with the [ReadOnly](../../../language-reference/modifiers/readonly.md) keyword.</span></span>

<span data-ttu-id="8f5ec-106">In den folgenden Situationen können Sie die Konstante [Anweisung](../../../language-reference/statements/const-statement.md) nicht verwenden, um einen konstanten Wert zu deklarieren und zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="8f5ec-106">You cannot use the [Const Statement](../../../language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>

- <span data-ttu-id="8f5ec-107">Die `Const` Anweisung akzeptiert nicht den Datentyp, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-107">The `Const` statement does not accept the data type you want to use</span></span>

- <span data-ttu-id="8f5ec-108">Der Wert ist zur Kompilierzeit nicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-108">You do not know the value at compile time</span></span>

- <span data-ttu-id="8f5ec-109">Der Konstante Wert kann zur Kompilierzeit nicht berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-109">You are unable to compute the constant value at compile time</span></span>

### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="8f5ec-110">So erstellen Sie eine Variable, die den Wert nicht ändert</span><span class="sxs-lookup"><span data-stu-id="8f5ec-110">To create a variable that does not change in value</span></span>

1. <span data-ttu-id="8f5ec-111">Deklarieren Sie auf Modulebene eine Member-Variable mit der [Dim-Anweisung](../../../language-reference/statements/dim-statement.md), und schließen Sie [das Schlüsselwort](../../../language-reference/modifiers/readonly.md) "schreibgeschützt" ein.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-111">At module level, declare a member variable with the [Dim Statement](../../../language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../language-reference/modifiers/readonly.md) keyword.</span></span>

    ```vb
    Dim ReadOnly timeStarted
    ```

    <span data-ttu-id="8f5ec-112">Sie können `ReadOnly` nur für eine Element Variable angeben.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="8f5ec-113">Dies bedeutet, dass Sie die Variable auf Modulebene außerhalb der Prozeduren definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-113">This means you must define the variable at module level, outside of any procedure.</span></span>

2. <span data-ttu-id="8f5ec-114">Wenn Sie den Wert in einer einzelnen Anweisung zur Kompilierzeit berechnen können, verwenden Sie eine Initialisierungs Klausel in der- `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="8f5ec-115">Befolgen Sie die [As](../../../language-reference/statements/as-clause.md) -Klausel mit einem Gleichheitszeichen ( `=` ), gefolgt von einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-115">Follow the [As](../../../language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="8f5ec-116">Stellen Sie sicher, dass der Compiler diesen Ausdruck mit einem konstanten Wert auswerten kann.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    <span data-ttu-id="8f5ec-117">Sie können einer `ReadOnly` Variablen nur einmal einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="8f5ec-118">Nachdem Sie dies getan haben, kann kein Code mehr seinen Wert ändern.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-118">Once you do so, no code can ever change its value.</span></span>

    <span data-ttu-id="8f5ec-119">Wenn Sie den Wert zur Kompilierzeit nicht kennen oder ihn zur Kompilierzeit nicht in einer einzelnen Anweisung berechnen können, können Sie ihn trotzdem zur Laufzeit in einem Konstruktor zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="8f5ec-120">Zu diesem Zweck müssen Sie die `ReadOnly` Variable auf Klassen-oder Struktur Ebene deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="8f5ec-121">Berechnen Sie im Konstruktor für diese Klasse oder Struktur den festgelegten Wert der Variablen, und weisen Sie ihn der Variablen zu, bevor Sie den Konstruktor zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8f5ec-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f5ec-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f5ec-122">See also</span></span>

- [<span data-ttu-id="8f5ec-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="8f5ec-123">WriteOnly</span></span>](../../../language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="8f5ec-124">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8f5ec-124">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)
