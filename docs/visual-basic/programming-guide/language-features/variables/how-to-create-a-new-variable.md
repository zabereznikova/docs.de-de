---
title: 'Vorgehensweise: Neue Variable erstellen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: a6cb7225ea203f0b38b731795684bfb0cfdfd2d1
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630897"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="da465-102">Vorgehensweise: Neue Variable erstellen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da465-102">How to: Create a New Variable (Visual Basic)</span></span>

<span data-ttu-id="da465-103">Sie erstellen eine Variable mit einer [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="da465-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

### <a name="to-create-a-new-variable"></a><span data-ttu-id="da465-104">So erstellen Sie eine neue Variable</span><span class="sxs-lookup"><span data-stu-id="da465-104">To create a new variable</span></span>

1. <span data-ttu-id="da465-105">Deklarieren Sie die Variable `Dim` in einer-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="da465-105">Declare the variable in a `Dim` statement.</span></span>

    ```vb
    Dim newCustomer
    ```

2. <span data-ttu-id="da465-106">Fügen Sie Spezifikationen für die Merkmale der Variablen ein, z. b. [private](../../../../visual-basic/language-reference/modifiers/private.md), [statische](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)oder [wiwitvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="da465-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="da465-107">Weitere Informationen finden Sie unter [deklarierte Element Eigenschaften](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="da465-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

    <span data-ttu-id="da465-108">Das `Dim` Schlüsselwort ist nicht erforderlich, wenn Sie andere Schlüsselwörter in der Deklaration verwenden.</span><span class="sxs-lookup"><span data-stu-id="da465-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>

3. <span data-ttu-id="da465-109">Befolgen Sie die Spezifikationen mit dem Variablennamen, der Visual Basic Regeln und Konventionen befolgt werden muss.</span><span class="sxs-lookup"><span data-stu-id="da465-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="da465-110">Weitere Informationen finden Sie unter [deklarierte Element Namen](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="da465-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

4. <span data-ttu-id="da465-111">Befolgen Sie den Namen mit der [As](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel, um den Datentyp der Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="da465-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>

    ```vb
    Public Static newCustomer As Customer
    ```

    <span data-ttu-id="da465-112">Wenn Sie den-Datentyp nicht angeben, wird der Standardwert verwendet `Object`:.</span><span class="sxs-lookup"><span data-stu-id="da465-112">If you do not specify the data type, it uses the default: `Object`.</span></span>

5. <span data-ttu-id="da465-113">Befolgen Sie `As` die-Klausel mit einem Gleichheitszeichen (`=`), und befolgen Sie das Gleichheitszeichen mit dem Anfangswert der Variablen.</span><span class="sxs-lookup"><span data-stu-id="da465-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>

    <span data-ttu-id="da465-114">Visual Basic weist der Variablen bei jedem Ausführen der `Dim` Anweisung den angegebenen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="da465-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="da465-115">Wenn Sie keinen Anfangswert angeben, weist Visual Basic den Standard Anfangswert für den Datentyp der Variablen zu, wenn er zum ersten Mal in den Code wechselt `Dim` , der die Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="da465-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>

    <span data-ttu-id="da465-116">Wenn die Variable ein Verweistyp ist, können Sie eine Instanz der zugehörigen Klasse erstellen, indem Sie das [neue Operator](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort in die `As` -Klausel einschließen.</span><span class="sxs-lookup"><span data-stu-id="da465-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="da465-117">Wenn Sie nicht verwenden `New`, ist der Anfangswert der Variablen " [Nothing](../../../../visual-basic/language-reference/nothing.md)".</span><span class="sxs-lookup"><span data-stu-id="da465-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a><span data-ttu-id="da465-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da465-118">See also</span></span>

- [<span data-ttu-id="da465-119">Variablen</span><span class="sxs-lookup"><span data-stu-id="da465-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="da465-120">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="da465-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="da465-121">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="da465-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="da465-122">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="da465-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="da465-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="da465-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="da465-124">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="da465-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="da465-125">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="da465-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="da465-126">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="da465-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
