---
title: 'Vorgehensweise: Label-Anweisungen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 69ec8c7625410f140c59ba8dd492dca76857eb96
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828640"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="b885f-102">Vorgehensweise: Label-Anweisungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b885f-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="b885f-103">Anweisungsblöcke bestehen von Codezeilen, die durch Doppelpunkte getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="b885f-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="b885f-104">Codezeilen, die eine identifizierende Zeichenfolge oder ganzen Zahl vorangestellt werden als *mit der Bezeichnung*.</span><span class="sxs-lookup"><span data-stu-id="b885f-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="b885f-105">Anweisungsbezeichnungen werden verwendet, um eine einzige Zeile Code für die Verwendung mit Anweisungen wie z. B. Identifikation markieren `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="b885f-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="b885f-106">Bezeichnungen können entweder gültiger Visual Basic-Bezeichner sein – z. B. die Programmierelemente identifizieren – oder Integer-Literale.</span><span class="sxs-lookup"><span data-stu-id="b885f-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="b885f-107">Eine Bezeichnung muss am Anfang einer Zeile des Quellcodes angezeigt werden und muss von einem Doppelpunkt, unabhängig davon, ob sie eine Anweisung in der gleichen Zeile folgt, wird gefolgt sein.</span><span class="sxs-lookup"><span data-stu-id="b885f-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="b885f-108">Der Compiler identifiziert Bezeichnungen wird geprüft, ob der Anfang der Zeile auf einen bereits definierten Bezeichner entspricht.</span><span class="sxs-lookup"><span data-stu-id="b885f-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="b885f-109">Wenn dies nicht der Fall ist, wird der Compiler davon ausgegangen, dass es sich um eine Bezeichnung ist.</span><span class="sxs-lookup"><span data-stu-id="b885f-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="b885f-110">Bezeichnungen müssen ihre eigenen Deklarationsabschnitt und verursachen keine Konflikte mit anderen Bezeichnern.</span><span class="sxs-lookup"><span data-stu-id="b885f-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="b885f-111">Eine Bezeichnung für den Bereich ist der Text der Methode.</span><span class="sxs-lookup"><span data-stu-id="b885f-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="b885f-112">Deklaration der Bezeichnung hat Vorrang vor in einer mehrdeutigen Situation.</span><span class="sxs-lookup"><span data-stu-id="b885f-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b885f-113">Bezeichnungen können nur auf ausführbaren Anweisungen in Methoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b885f-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="b885f-114">Um eine einzige Zeile Code zu beschriften.</span><span class="sxs-lookup"><span data-stu-id="b885f-114">To label a line of code</span></span>  
  
-   <span data-ttu-id="b885f-115">Fügen Sie einen Bezeichner, gefolgt von einem Doppelpunkt am Anfang der Zeile des Quellcodes.</span><span class="sxs-lookup"><span data-stu-id="b885f-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="b885f-116">Z. B. die folgenden Codezeilen sind mit der Bezeichnung `Jump` und `120`bzw.:</span><span class="sxs-lookup"><span data-stu-id="b885f-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]  
  
## <a name="see-also"></a><span data-ttu-id="b885f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b885f-117">See also</span></span>

- [<span data-ttu-id="b885f-118">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="b885f-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="b885f-119">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="b885f-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="b885f-120">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="b885f-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
