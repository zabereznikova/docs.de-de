---
title: REM-Anweisung (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 3bd526b08e1ba3be856e1e823cf8ef49ea9b6c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604275"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="f3caa-102">REM-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3caa-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="f3caa-103">Verwendet für erläuternde Hinweise im Quellcode eines Programms.</span><span class="sxs-lookup"><span data-stu-id="f3caa-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3caa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3caa-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="f3caa-105">Teile</span><span class="sxs-lookup"><span data-stu-id="f3caa-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="f3caa-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="f3caa-106">Optional.</span></span> <span data-ttu-id="f3caa-107">Der Text eines Kommentars, die Sie einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="f3caa-107">The text of any comment you want to include.</span></span> <span data-ttu-id="f3caa-108">Ein Leerzeichen ist erforderlich, zwischen den `REM` Schlüsselwort und `comment`.</span><span class="sxs-lookup"><span data-stu-id="f3caa-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3caa-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f3caa-109">Remarks</span></span>  
 <span data-ttu-id="f3caa-110">Sie setzen eine `REM` Anweisung allein auf einer Zeile, oder Sie können es in einer Zeile, die nach einer anderen Anweisung ablegen.</span><span class="sxs-lookup"><span data-stu-id="f3caa-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="f3caa-111">Die `REM` Anweisung muss die letzte Anweisung in der Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="f3caa-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="f3caa-112">Wenn es sich um eine andere Anweisung folgt die `REM` müssen von dieser Anweisung durch ein Leerzeichen getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="f3caa-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="f3caa-113">Sie können ein einfaches Anführungszeichen (`'`) anstelle von `REM`.</span><span class="sxs-lookup"><span data-stu-id="f3caa-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="f3caa-114">Dies ist "true", gibt an, ob der Kommentar folgt von einer anderen Anweisung in der gleichen Zeile oder alleine in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="f3caa-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3caa-115">Sie können nicht fortfahren eine `REM` Anweisung, indem Sie eine Zeilenfortsetzungszeichenfolge (`_`).</span><span class="sxs-lookup"><span data-stu-id="f3caa-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="f3caa-116">Nachdem ein Kommentar eingeleitet wurde, wird der Compiler nicht die Zeichen für eine besondere Bedeutung untersuchen.</span><span class="sxs-lookup"><span data-stu-id="f3caa-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="f3caa-117">Verwenden Sie für einen mehrzeiligen Kommentar eine andere `REM` -Anweisung oder das Kommentarsymbol (`'`) in jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="f3caa-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3caa-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3caa-118">Example</span></span>  
 <span data-ttu-id="f3caa-119">Das folgende Beispiel veranschaulicht die `REM` -Anweisung, die für erläuternde Hinweise in einem Programm verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f3caa-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="f3caa-120">Darüber hinaus wird gezeigt, die Alternative Verwendung der einfachen Anführungszeichen (`'`) anstelle von `REM`.</span><span class="sxs-lookup"><span data-stu-id="f3caa-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f3caa-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3caa-121">See Also</span></span>  
 [<span data-ttu-id="f3caa-122">Kommentare in Code</span><span class="sxs-lookup"><span data-stu-id="f3caa-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [<span data-ttu-id="f3caa-123">Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="f3caa-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
