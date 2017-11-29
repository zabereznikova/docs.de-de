---
title: REM-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d64ce970e3e74437f5e8c63c8a4d578900902192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="184a3-102">REM-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="184a3-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="184a3-103">Verwendet für erläuternde Hinweise im Quellcode eines Programms.</span><span class="sxs-lookup"><span data-stu-id="184a3-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="184a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="184a3-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="184a3-105">Teile</span><span class="sxs-lookup"><span data-stu-id="184a3-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="184a3-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="184a3-106">Optional.</span></span> <span data-ttu-id="184a3-107">Der Text eines Kommentars, die Sie einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="184a3-107">The text of any comment you want to include.</span></span> <span data-ttu-id="184a3-108">Ein Leerzeichen ist erforderlich, zwischen den `REM` Schlüsselwort und `comment`.</span><span class="sxs-lookup"><span data-stu-id="184a3-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="184a3-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="184a3-109">Remarks</span></span>  
 <span data-ttu-id="184a3-110">Sie setzen eine `REM` Anweisung allein auf einer Zeile, oder Sie können es in einer Zeile, die nach einer anderen Anweisung ablegen.</span><span class="sxs-lookup"><span data-stu-id="184a3-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="184a3-111">Die `REM` Anweisung muss die letzte Anweisung in der Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="184a3-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="184a3-112">Wenn es sich um eine andere Anweisung folgt die `REM` müssen von dieser Anweisung durch ein Leerzeichen getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="184a3-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="184a3-113">Sie können ein einfaches Anführungszeichen (`'`) anstelle von `REM`.</span><span class="sxs-lookup"><span data-stu-id="184a3-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="184a3-114">Dies ist "true", gibt an, ob der Kommentar folgt von einer anderen Anweisung in der gleichen Zeile oder alleine in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="184a3-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="184a3-115">Sie können nicht fortfahren eine `REM` Anweisung, indem Sie eine Zeilenfortsetzungszeichenfolge (`_`).</span><span class="sxs-lookup"><span data-stu-id="184a3-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="184a3-116">Nachdem ein Kommentar eingeleitet wurde, wird der Compiler nicht die Zeichen für eine besondere Bedeutung untersuchen.</span><span class="sxs-lookup"><span data-stu-id="184a3-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="184a3-117">Verwenden Sie für einen mehrzeiligen Kommentar eine andere `REM` -Anweisung oder das Kommentarsymbol (`'`) in jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="184a3-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="184a3-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="184a3-118">Example</span></span>  
 <span data-ttu-id="184a3-119">Das folgende Beispiel veranschaulicht die `REM` -Anweisung, die für erläuternde Hinweise in einem Programm verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="184a3-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="184a3-120">Darüber hinaus wird gezeigt, die Alternative Verwendung der einfachen Anführungszeichen (`'`) anstelle von `REM`.</span><span class="sxs-lookup"><span data-stu-id="184a3-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="184a3-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="184a3-121">See Also</span></span>  
 [<span data-ttu-id="184a3-122">Kommentare in Code</span><span class="sxs-lookup"><span data-stu-id="184a3-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [<span data-ttu-id="184a3-123">Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="184a3-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
