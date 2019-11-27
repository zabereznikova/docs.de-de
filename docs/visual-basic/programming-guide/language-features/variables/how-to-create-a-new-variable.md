---
title: 'Gewusst wie: Erstellen einer neuen Variablen'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: 2a2b5b8bef3b66f9727f0e65b61882186c007e94
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353633"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="03419-102">Gewusst wie: Erstellen einer neuen Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03419-102">How to: Create a New Variable (Visual Basic)</span></span>

<span data-ttu-id="03419-103">Sie erstellen eine Variable mit einer [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="03419-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

### <a name="to-create-a-new-variable"></a><span data-ttu-id="03419-104">So erstellen Sie eine neue Variable</span><span class="sxs-lookup"><span data-stu-id="03419-104">To create a new variable</span></span>

1. <span data-ttu-id="03419-105">Deklarieren Sie die Variable in einer `Dim`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="03419-105">Declare the variable in a `Dim` statement.</span></span>

    ```vb
    Dim newCustomer
    ```

2. <span data-ttu-id="03419-106">Fügen Sie Spezifikationen für die Merkmale der Variablen ein, z. b. [private](../../../../visual-basic/language-reference/modifiers/private.md), [statische](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)oder [wiwitvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="03419-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="03419-107">Weitere Informationen finden Sie unter [deklarierte Element Eigenschaften](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="03419-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

    <span data-ttu-id="03419-108">Sie benötigen das `Dim`-Schlüsselwort nicht, wenn Sie andere Schlüsselwörter in der Deklaration verwenden.</span><span class="sxs-lookup"><span data-stu-id="03419-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>

3. <span data-ttu-id="03419-109">Befolgen Sie die Spezifikationen mit dem Variablennamen, der Visual Basic Regeln und Konventionen befolgt werden muss.</span><span class="sxs-lookup"><span data-stu-id="03419-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="03419-110">Weitere Informationen finden Sie unter [deklarierte Element Namen](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="03419-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

4. <span data-ttu-id="03419-111">Befolgen Sie den Namen mit der [As](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel, um den Datentyp der Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="03419-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>

    ```vb
    Public Static newCustomer As Customer
    ```

    <span data-ttu-id="03419-112">Wenn Sie den-Datentyp nicht angeben, wird der Standardwert verwendet: `Object`.</span><span class="sxs-lookup"><span data-stu-id="03419-112">If you do not specify the data type, it uses the default: `Object`.</span></span>

5. <span data-ttu-id="03419-113">Befolgen Sie die `As`-Klausel mit einem Gleichheitszeichen (`=`), und befolgen Sie das Gleichheitszeichen mit dem Anfangswert der Variablen.</span><span class="sxs-lookup"><span data-stu-id="03419-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>

    <span data-ttu-id="03419-114">Visual Basic weist der Variablen bei jedem Ausführen der `Dim` Anweisung den angegebenen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="03419-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="03419-115">Wenn Sie keinen Anfangswert angeben, weist Visual Basic den Standard Anfangswert für den Datentyp der Variablen zu, wenn er das erste Mal in den Code eingibt, der die `Dim` Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="03419-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>

    <span data-ttu-id="03419-116">Wenn die Variable ein Verweistyp ist, können Sie eine Instanz der zugehörigen Klasse erstellen, indem Sie das [neue Operator](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort in der `As`-Klausel einschließen.</span><span class="sxs-lookup"><span data-stu-id="03419-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="03419-117">Wenn Sie `New`nicht verwenden, ist der Anfangswert der Variablen " [Nothing](../../../../visual-basic/language-reference/nothing.md)".</span><span class="sxs-lookup"><span data-stu-id="03419-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a><span data-ttu-id="03419-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03419-118">See also</span></span>

- [<span data-ttu-id="03419-119">Variablen</span><span class="sxs-lookup"><span data-stu-id="03419-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="03419-120">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="03419-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="03419-121">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="03419-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="03419-122">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="03419-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="03419-123">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="03419-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="03419-124">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="03419-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="03419-125">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="03419-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="03419-126">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="03419-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
