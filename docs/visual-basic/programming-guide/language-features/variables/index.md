---
title: Variables
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: bd6417033a6c2626d17ad003de6c637dd1e8adaa
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080217"
---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="5d6e6-102">Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d6e6-102">Variables in Visual Basic</span></span>

<span data-ttu-id="5d6e6-103">Sie müssen häufig Werte speichern, wenn Sie Berechnungen mit Visual Basic durchführen.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-103">You often have to store values when you perform calculations with Visual Basic.</span></span> <span data-ttu-id="5d6e6-104">Sie möchten z.B. mehrere Werte berechnen, sie vergleichen und je nach Ergebnis des Vergleichs unterschiedliche Vorgänge auf diesen ausführen.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-104">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="5d6e6-105">Sie müssen die Werte beibehalten, wenn Sie sie vergleichen möchten.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-105">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="5d6e6-106">Verbrauch</span><span class="sxs-lookup"><span data-stu-id="5d6e6-106">Usage</span></span>  

 <span data-ttu-id="5d6e6-107">Visual Basic wie die meisten Programmiersprachen verwendet Variablen zum Speichern von Werten.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-107">Visual Basic, just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="5d6e6-108">Eine *Variable* besitzt einen Namen (das Wort, das Sie verwenden, wenn Sie sich auf den Wert beziehen, den die Variable enthält).</span><span class="sxs-lookup"><span data-stu-id="5d6e6-108">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="5d6e6-109">Eine Variable verfügt auch über einen Datentyp (der die Art der Daten bestimmt, die die Variable speichern kann).</span><span class="sxs-lookup"><span data-stu-id="5d6e6-109">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="5d6e6-110">Eine Variable kann ein Array darstellen, wenn sie einen indizierten Satz von eng verwandten Datenelementen speichern muss.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-110">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="5d6e6-111">Durch den lokalen Typrückschluss können Sie Variablen deklarieren, ohne explizit einen Datentyp angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-111">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="5d6e6-112">Der Compiler leitet stattdessen den Typ der Variablen vom Typ des Initialisiererausdrucks ab.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-112">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="5d6e6-113">Weitere Informationen finden Sie unter [Local Type Inference (Lokaler Typrückschluss)](local-type-inference.md) und [Option Infer Statement (Option Infer-Anweisung)](../../../language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5d6e6-113">For more information, see [Local Type Inference](local-type-inference.md) and [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="5d6e6-114">Zuweisen von Werten</span><span class="sxs-lookup"><span data-stu-id="5d6e6-114">Assigning Values</span></span>  

 <span data-ttu-id="5d6e6-115">Sie verwenden Zuweisungsanweisungen, um Berechnungen durchzuführen und das Ergebnis einer Variable zuzuweisen, so wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-115">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
> <span data-ttu-id="5d6e6-116">Das Gleichheitszeichen (`=`) ist in diesem Beispiel ein Zuweisungsoperator, kein Gleichheitsoperator.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-116">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="5d6e6-117">Der Wert wird der `applesSold`-Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-117">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="5d6e6-118">Weitere Informationen finden Sie unter [Vorgehensweise: Verschieben von Daten in und aus einer Variablen](how-to-move-data-into-and-out-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="5d6e6-118">For more information, see [How to: Move Data Into and Out of a Variable](how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="5d6e6-119">Variablen und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5d6e6-119">Variables and Properties</span></span>  

 <span data-ttu-id="5d6e6-120">Wie eine Variable stellt auch eine *Eigenschaft* einen Wert dar, auf den Sie zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-120">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="5d6e6-121">Jedoch ist er komplexer als eine Variable.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-121">However, it is more complex than a variable.</span></span> <span data-ttu-id="5d6e6-122">Eine Eigenschaft verwendet Codeblöcke, die steuern, wie der Wert festgelegt und abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5d6e6-122">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="5d6e6-123">Weitere Informationen finden Sie unter [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](../procedures/differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="5d6e6-123">For more information, see [Differences Between Properties and Variables in Visual Basic](../procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6e6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d6e6-124">See also</span></span>

- [<span data-ttu-id="5d6e6-125">Variablen Deklaration</span><span class="sxs-lookup"><span data-stu-id="5d6e6-125">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="5d6e6-126">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="5d6e6-126">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="5d6e6-127">Problembehandlung bei Variablen</span><span class="sxs-lookup"><span data-stu-id="5d6e6-127">Troubleshooting Variables</span></span>](troubleshooting-variables.md)
- [<span data-ttu-id="5d6e6-128">Vorgehensweise: Verschieben von Daten in eine und aus einer Variablen</span><span class="sxs-lookup"><span data-stu-id="5d6e6-128">How to: Move Data Into and Out of a Variable</span></span>](how-to-move-data-into-and-out-of-a-variable.md)
- [<span data-ttu-id="5d6e6-129">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d6e6-129">Differences Between Properties and Variables in Visual Basic</span></span>](../procedures/differences-between-properties-and-variables.md)
- [<span data-ttu-id="5d6e6-130">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="5d6e6-130">Local Type Inference</span></span>](local-type-inference.md)
