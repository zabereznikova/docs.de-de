---
title: 'Gewusst wie: Erstellen einer neuen Variablen (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Dim statement
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 3b5aa4e5e0b84f41ac3df73bc70d8402d10b21a2
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="4393d-102">Gewusst wie: Erstellen einer neuen Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4393d-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="4393d-103">Erstellen Sie eine Variable mit einem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4393d-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="4393d-104">So erstellen Sie eine neue Variable</span><span class="sxs-lookup"><span data-stu-id="4393d-104">To create a new variable</span></span>  
  
1.  <span data-ttu-id="4393d-105">Deklarieren Sie die Variable in eine `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4393d-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  <span data-ttu-id="4393d-106">Nehmen Sie Angaben zur Merkmale der Variablen, wie z. B. [Private](../../../../visual-basic/language-reference/modifiers/private.md), [statische](../../../../visual-basic/language-reference/modifiers/static.md), [Schatten](../../../../visual-basic/language-reference/modifiers/shadows.md), oder [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="4393d-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="4393d-107">Weitere Informationen finden Sie unter [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="4393d-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="4393d-108">Sie müssen nicht die `Dim` -Schlüsselwort verwenden, wenn Sie andere Schlüsselwörter in der Deklaration verwenden.</span><span class="sxs-lookup"><span data-stu-id="4393d-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3.  <span data-ttu-id="4393d-109">Führen Sie die Namen der Variablen muss die Spezifikationen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Regeln und Konventionen.</span><span class="sxs-lookup"><span data-stu-id="4393d-109">Follow the specifications with the variable's name, which must follow [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] rules and conventions.</span></span> <span data-ttu-id="4393d-110">Weitere Informationen finden Sie unter [Elementnamen deklariert](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="4393d-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  <span data-ttu-id="4393d-111">Führen Sie den Namen der [als](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel, um den Datentyp der Variablen angeben.</span><span class="sxs-lookup"><span data-stu-id="4393d-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="4393d-112">Wenn Sie den Datentyp nicht angeben, wird standardmäßig verwendet: `Object`.</span><span class="sxs-lookup"><span data-stu-id="4393d-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5.  <span data-ttu-id="4393d-113">Führen Sie die `As` -Klausel mit einem Gleichheitszeichen (`=`) und nach dem Gleichheitszeichen Anfangswert der Variablen.</span><span class="sxs-lookup"><span data-stu-id="4393d-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="4393d-114">weist den angegebenen Wert der Variable, jeder Ausführung der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4393d-114"> assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="4393d-115">Wenn Sie keinen Anfangswert angeben [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] der anfängliche Standardwert für den Datentyp der Variablen zugewiesen, wenn sie zunächst den Code eingibt, der enthält die `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4393d-115">If you do not specify an initial value, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="4393d-116">Wenn die Variable ein Verweistyp ist, können Sie eine Instanz der Klasse erstellen, mit der [Operator New](../../../../visual-basic/language-reference/operators/new-operator.md) -Schlüsselwort in der `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="4393d-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="4393d-117">Wenn Sie keine verwenden `New`, ist der Anfangswert der Variablen [nichts](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="4393d-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4393d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4393d-118">See Also</span></span>  
 <span data-ttu-id="4393d-119">[Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span><span class="sxs-lookup"><span data-stu-id="4393d-119">[Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span></span>  
<span data-ttu-id="4393d-120"> [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="4393d-120"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="4393d-121"> [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="4393d-121"> [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="4393d-122"> [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="4393d-122"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="4393d-123"> [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="4393d-123"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="4393d-124"> [Anweisungen](../../../../visual-basic/language-reference/statements/index.md) </span><span class="sxs-lookup"><span data-stu-id="4393d-124"> [Statements](../../../../visual-basic/language-reference/statements/index.md) </span></span>  
<span data-ttu-id="4393d-125"> [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="4393d-125"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="4393d-126"> [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span><span class="sxs-lookup"><span data-stu-id="4393d-126"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span></span>

