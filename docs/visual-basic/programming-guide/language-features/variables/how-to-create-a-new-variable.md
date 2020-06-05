---
title: 'Vorgehensweise: Erstellen einer neuen Variablen'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: 501c8f3aff4c5b204d231bdc26213e13d125a7cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410528"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="99e4a-102">Gewusst wie: Erstellen einer neuen Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99e4a-102">How to: Create a New Variable (Visual Basic)</span></span>

<span data-ttu-id="99e4a-103">Sie erstellen eine Variable mit einer [Dim-Anweisung](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="99e4a-103">You create a variable with a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span>

### <a name="to-create-a-new-variable"></a><span data-ttu-id="99e4a-104">So erstellen Sie eine neue Variable</span><span class="sxs-lookup"><span data-stu-id="99e4a-104">To create a new variable</span></span>

1. <span data-ttu-id="99e4a-105">Deklarieren Sie die Variable in einer- `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="99e4a-105">Declare the variable in a `Dim` statement.</span></span>

    ```vb
    Dim newCustomer
    ```

2. <span data-ttu-id="99e4a-106">Fügen Sie Spezifikationen für die Merkmale der Variablen ein, z. b. [private](../../../language-reference/modifiers/private.md), [statische](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md)oder [wiwitvents](../../../language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="99e4a-106">Include specifications for the variable's characteristics, such as [Private](../../../language-reference/modifiers/private.md), [Static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md), or [WithEvents](../../../language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="99e4a-107">Weitere Informationen finden Sie unter [deklarierte Element Eigenschaften](../declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="99e4a-107">For more information, see [Declared Element Characteristics](../declared-elements/declared-element-characteristics.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

    <span data-ttu-id="99e4a-108">Das `Dim` Schlüsselwort ist nicht erforderlich, wenn Sie andere Schlüsselwörter in der Deklaration verwenden.</span><span class="sxs-lookup"><span data-stu-id="99e4a-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>

3. <span data-ttu-id="99e4a-109">Befolgen Sie die Spezifikationen mit dem Variablennamen, der Visual Basic Regeln und Konventionen befolgt werden muss.</span><span class="sxs-lookup"><span data-stu-id="99e4a-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="99e4a-110">Weitere Informationen finden Sie unter [deklarierte Element Namen](../declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="99e4a-110">For more information, see [Declared Element Names](../declared-elements/declared-element-names.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

4. <span data-ttu-id="99e4a-111">Befolgen Sie den Namen mit der [As](../../../language-reference/statements/as-clause.md) -Klausel, um den Datentyp der Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="99e4a-111">Follow the name with the [As](../../../language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>

    ```vb
    Public Static newCustomer As Customer
    ```

    <span data-ttu-id="99e4a-112">Wenn Sie den-Datentyp nicht angeben, wird der Standardwert verwendet: `Object` .</span><span class="sxs-lookup"><span data-stu-id="99e4a-112">If you do not specify the data type, it uses the default: `Object`.</span></span>

5. <span data-ttu-id="99e4a-113">Befolgen Sie die `As` -Klausel mit einem Gleichheitszeichen ( `=` ), und befolgen Sie das Gleichheitszeichen mit dem Anfangswert der Variablen.</span><span class="sxs-lookup"><span data-stu-id="99e4a-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>

    <span data-ttu-id="99e4a-114">Visual Basic weist der Variablen bei jedem Ausführen der Anweisung den angegebenen Wert zu `Dim` .</span><span class="sxs-lookup"><span data-stu-id="99e4a-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="99e4a-115">Wenn Sie keinen Anfangswert angeben, weist Visual Basic den Standard Anfangswert für den Datentyp der Variablen zu, wenn er zum ersten Mal in den Code wechselt, der die `Dim` Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="99e4a-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>

    <span data-ttu-id="99e4a-116">Wenn die Variable ein Verweistyp ist, können Sie eine Instanz der zugehörigen Klasse erstellen, indem Sie das [neue Operator](../../../language-reference/operators/new-operator.md) Schlüsselwort in die- `As` Klausel einschließen.</span><span class="sxs-lookup"><span data-stu-id="99e4a-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="99e4a-117">Wenn Sie nicht verwenden `New` , ist der Anfangswert der Variablen " [Nothing](../../../language-reference/nothing.md)".</span><span class="sxs-lookup"><span data-stu-id="99e4a-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../language-reference/nothing.md).</span></span>

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a><span data-ttu-id="99e4a-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99e4a-118">See also</span></span>

- [<span data-ttu-id="99e4a-119">Variablen</span><span class="sxs-lookup"><span data-stu-id="99e4a-119">Variables</span></span>](index.md)
- [<span data-ttu-id="99e4a-120">Variablen Deklaration</span><span class="sxs-lookup"><span data-stu-id="99e4a-120">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="99e4a-121">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="99e4a-121">Declared Element Names</span></span>](../declared-elements/declared-element-names.md)
- [<span data-ttu-id="99e4a-122">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="99e4a-122">Declared Element Characteristics</span></span>](../declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="99e4a-123">Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="99e4a-123">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="99e4a-124">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="99e4a-124">Statements</span></span>](../../../language-reference/statements/index.md)
- [<span data-ttu-id="99e4a-125">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="99e4a-125">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="99e4a-126">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="99e4a-126">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
