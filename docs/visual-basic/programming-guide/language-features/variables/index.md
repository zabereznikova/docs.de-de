---
title: Variablen in Visual Basic
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
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2fdc670bf4f17000809e75e32c32edb39abf0fed
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="abfec-102">Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abfec-102">Variables in Visual Basic</span></span>
<span data-ttu-id="abfec-103">Sie müssen oft Werte speichern, wenn Sie Berechnungen mit [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] durchführen.</span><span class="sxs-lookup"><span data-stu-id="abfec-103">You often have to store values when you perform calculations with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="abfec-104">Sie möchten z.B. mehrere Werte berechnen, sie vergleichen und je nach Ergebnis des Vergleichs unterschiedliche Vorgänge auf diesen ausführen.</span><span class="sxs-lookup"><span data-stu-id="abfec-104">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="abfec-105">Sie müssen die Werte beibehalten, wenn Sie sie vergleichen möchten.</span><span class="sxs-lookup"><span data-stu-id="abfec-105">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="abfec-106">Verwendung</span><span class="sxs-lookup"><span data-stu-id="abfec-106">Usage</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="abfec-107"> verwendet genauso wie die meisten Programmiersprachen Variablen zum Speichern von Werten.</span><span class="sxs-lookup"><span data-stu-id="abfec-107">, just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="abfec-108">Eine *Variable* besitzt einen Namen (das Wort, das Sie verwenden, wenn Sie sich auf den Wert beziehen, den die Variable enthält).</span><span class="sxs-lookup"><span data-stu-id="abfec-108">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="abfec-109">Eine Variable verfügt auch über einen Datentyp (der die Art der Daten bestimmt, die die Variable speichern kann).</span><span class="sxs-lookup"><span data-stu-id="abfec-109">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="abfec-110">Eine Variable kann ein Array darstellen, wenn sie einen indizierten Satz von eng verwandten Datenelementen speichern muss.</span><span class="sxs-lookup"><span data-stu-id="abfec-110">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="abfec-111">Durch den lokalen Typrückschluss können Sie Variablen deklarieren, ohne explizit einen Datentyp angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="abfec-111">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="abfec-112">Der Compiler leitet stattdessen den Typ der Variablen vom Typ des Initialisiererausdrucks ab.</span><span class="sxs-lookup"><span data-stu-id="abfec-112">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="abfec-113">Weitere Informationen finden Sie unter [Local Type Inference (Lokaler Typrückschluss)](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) und [Option Infer Statement (Option Infer-Anweisung)](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="abfec-113">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="abfec-114">Zuweisen von Werten</span><span class="sxs-lookup"><span data-stu-id="abfec-114">Assigning Values</span></span>  
 <span data-ttu-id="abfec-115">Sie verwenden Zuweisungsanweisungen, um Berechnungen durchzuführen und das Ergebnis einer Variable zuzuweisen, so wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="abfec-115">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 <span data-ttu-id="abfec-116">[!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="abfec-116">[!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abfec-117">Das Gleichheitszeichen (`=`) ist in diesem Beispiel ein Zuweisungsoperator, kein Gleichheitsoperator.</span><span class="sxs-lookup"><span data-stu-id="abfec-117">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="abfec-118">Der Wert wird der `applesSold`-Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="abfec-118">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="abfec-119">Weitere Informationen finden Sie unter [Vorgehensweise: Verschieben von Daten in und aus einer Variablen](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="abfec-119">For more information, see [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="abfec-120">Variablen und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="abfec-120">Variables and Properties</span></span>  
 <span data-ttu-id="abfec-121">Wie eine Variable stellt auch eine *Eigenschaft* einen Wert dar, auf den Sie zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="abfec-121">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="abfec-122">Jedoch ist er komplexer als eine Variable.</span><span class="sxs-lookup"><span data-stu-id="abfec-122">However, it is more complex than a variable.</span></span> <span data-ttu-id="abfec-123">Eine Eigenschaft verwendet Codeblöcke, die steuern, wie der Wert festgelegt und abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="abfec-123">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="abfec-124">Weitere Informationen finden Sie unter [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="abfec-124">For more information, see [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abfec-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abfec-125">See Also</span></span>  
 <span data-ttu-id="abfec-126">[Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="abfec-126">[Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
 <span data-ttu-id="abfec-127">[Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="abfec-127">[Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
 <span data-ttu-id="abfec-128">[Problembehandlung bei Variablen](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md) </span><span class="sxs-lookup"><span data-stu-id="abfec-128">[Troubleshooting Variables](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md) </span></span>  
 <span data-ttu-id="abfec-129">[Vorgehensweise: Verschieben von Daten in und aus einer Variablen](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="abfec-129">[How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span></span>  
 <span data-ttu-id="abfec-130">[Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="abfec-130">[Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) </span></span>  
 [<span data-ttu-id="abfec-131">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="abfec-131">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

