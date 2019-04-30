---
title: 'Vorgehensweise: Erstellen einer neuen Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: ee1e93b4e9819992f17738eb024004a4d66210d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938241"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="75bba-102">Vorgehensweise: Erstellen einer neuen Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75bba-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="75bba-103">Erstellen Sie eine Variable mit einem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="75bba-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="75bba-104">So erstellen Sie eine neue Variable</span><span class="sxs-lookup"><span data-stu-id="75bba-104">To create a new variable</span></span>  
  
1. <span data-ttu-id="75bba-105">Deklarieren Sie die Variable in einem `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="75bba-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2. <span data-ttu-id="75bba-106">Nehmen Sie die Angaben zur der Merkmale der Variablen, wie z. B. [Private](../../../../visual-basic/language-reference/modifiers/private.md), [statische](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), oder [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="75bba-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="75bba-107">Weitere Informationen finden Sie unter [Merkmale der deklarierten Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="75bba-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="75bba-108">Sie müssen nicht die `Dim` Schlüsselwort, wenn Sie andere Schlüsselwörter in der Deklaration verwenden.</span><span class="sxs-lookup"><span data-stu-id="75bba-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3. <span data-ttu-id="75bba-109">Führen Sie die Spezifikationen mit den Namen der Variablen, die Visual Basic-Regeln und Konventionen folgen müssen.</span><span class="sxs-lookup"><span data-stu-id="75bba-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="75bba-110">Weitere Informationen finden Sie unter [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="75bba-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4. <span data-ttu-id="75bba-111">Führen Sie den Namen der [als](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel, um die Variable den Datentyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="75bba-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="75bba-112">Wenn Sie den Datentyp nicht angeben, verwendet dieser den Standardwert: `Object`.</span><span class="sxs-lookup"><span data-stu-id="75bba-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5. <span data-ttu-id="75bba-113">Führen Sie die `As` -Klausel mit einem Gleichheitszeichen (`=`), und befolgen Sie das Gleichheitszeichen mit dem Anfangswert der Variablen.</span><span class="sxs-lookup"><span data-stu-id="75bba-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     <span data-ttu-id="75bba-114">Visual Basic weist den angegebenen Wert der Variable, jeder Ausführung der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="75bba-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="75bba-115">Wenn Sie keinen Anfangswert angeben, weist Visual Basic der anfängliche Standardwert für die Variable den Datentyp an, wenn es zuerst den Code eingibt, der enthält die `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="75bba-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="75bba-116">Wenn die Variable ein Verweistyp ist, können Sie eine Instanz der Klasse erstellen, mit der [neuer Operator](../../../../visual-basic/language-reference/operators/new-operator.md) -Schlüsselwort in der `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="75bba-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="75bba-117">Wenn Sie nicht verwenden `New`, ist der Anfangswert der Variablen [nichts](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="75bba-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="75bba-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75bba-118">See also</span></span>

- [<span data-ttu-id="75bba-119">Variablen</span><span class="sxs-lookup"><span data-stu-id="75bba-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="75bba-120">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="75bba-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="75bba-121">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="75bba-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="75bba-122">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="75bba-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="75bba-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="75bba-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="75bba-124">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="75bba-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="75bba-125">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="75bba-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="75bba-126">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75bba-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
