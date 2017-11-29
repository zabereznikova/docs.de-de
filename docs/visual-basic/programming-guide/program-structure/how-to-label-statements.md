---
title: 'Gewusst wie: Label-Anweisungen (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 190ec9fc2392e6e4adae9b2b612edd69d73cedfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="62c9c-102">Gewusst wie: Label-Anweisungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62c9c-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="62c9c-103">Anweisungsblöcke erfolgen der Codezeilen, die durch Doppelpunkte getrennt.</span><span class="sxs-lookup"><span data-stu-id="62c9c-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="62c9c-104">Codezeilen, die eine identifizierende Zeichenfolge oder eine ganze Zahl vorangestellt werden als *mit der Bezeichnung*.</span><span class="sxs-lookup"><span data-stu-id="62c9c-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="62c9c-105">Anweisungsbezeichnungen dienen zum Kennzeichnen einer Zeile des Codes für die Verwendung mit Anweisungen wie z. B. dienen `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="62c9c-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="62c9c-106">Bezeichnungen können entweder gültiger Visual Basic-Bezeichner sein – z. B. solche, die Programmierelemente identifizieren – oder Integer-Literale.</span><span class="sxs-lookup"><span data-stu-id="62c9c-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="62c9c-107">Eine Bezeichnung muss am Anfang einer Zeile des Quellcodes angezeigt werden und muss unabhängig davon, ob sie eine Anweisung in der gleichen Zeile folgt, wird ein Doppelpunkt folgen.</span><span class="sxs-lookup"><span data-stu-id="62c9c-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="62c9c-108">Der Compiler identifiziert Bezeichnungen, indem Sie überprüfen, ob der Anfang der Zeile eine bereits definierte Bezeichner entspricht.</span><span class="sxs-lookup"><span data-stu-id="62c9c-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="62c9c-109">Ist dies nicht der Fall ist, wird der Compiler davon ausgegangen, dass es sich um eine Bezeichnung ist.</span><span class="sxs-lookup"><span data-stu-id="62c9c-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="62c9c-110">Bezeichnungen haben ihre eigenen Deklarationsabschnitt und verursachen keine Konflikte mit anderen Bezeichnern.</span><span class="sxs-lookup"><span data-stu-id="62c9c-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="62c9c-111">Eine Bezeichnung Bereich ist der Text der Methode.</span><span class="sxs-lookup"><span data-stu-id="62c9c-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="62c9c-112">Bezeichnungsdeklaration hat Vorrang vor in allen Situationen mit mehrdeutig.</span><span class="sxs-lookup"><span data-stu-id="62c9c-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62c9c-113">Bezeichnungen können nur auf die ausführbaren Anweisungen in Methoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62c9c-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="62c9c-114">Um eine Codezeile zu bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="62c9c-114">To label a line of code</span></span>  
  
-   <span data-ttu-id="62c9c-115">Platzieren Sie einen Bezeichner zeigen, gefolgt von einem Doppelpunkt am Anfang der Zeile des Quellcodes.</span><span class="sxs-lookup"><span data-stu-id="62c9c-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="62c9c-116">Z. B. die folgenden Codezeilen mit beschriftet `Jump` und `120`bzw.:</span><span class="sxs-lookup"><span data-stu-id="62c9c-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="62c9c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62c9c-117">See Also</span></span>  
 [<span data-ttu-id="62c9c-118">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="62c9c-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="62c9c-119">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="62c9c-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="62c9c-120">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="62c9c-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
