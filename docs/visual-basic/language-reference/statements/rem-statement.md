---
title: REM-Anweisung
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
ms.openlocfilehash: 6161a9f7e589988882b5f76477bc069afd2b9b41
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871949"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="c06b7-102">REM-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c06b7-102">REM Statement (Visual Basic)</span></span>

<span data-ttu-id="c06b7-103">Wird verwendet, um Erläuternde Hinweise in den Quellcode eines Programms einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="c06b7-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c06b7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c06b7-104">Syntax</span></span>  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="c06b7-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="c06b7-105">Parts</span></span>  

 `comment`  
 <span data-ttu-id="c06b7-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c06b7-106">Optional.</span></span> <span data-ttu-id="c06b7-107">Der Text eines beliebigen Kommentars, den Sie einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="c06b7-107">The text of any comment you want to include.</span></span> <span data-ttu-id="c06b7-108">Zwischen dem `REM` -Schlüsselwort und ist ein Leerzeichen erforderlich `comment` .</span><span class="sxs-lookup"><span data-stu-id="c06b7-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c06b7-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c06b7-109">Remarks</span></span>  

 <span data-ttu-id="c06b7-110">Sie können eine- `REM` Anweisung einzeln in eine Zeile einfügen, oder Sie können Sie in einer Zeile nach einer anderen Anweisung platzieren.</span><span class="sxs-lookup"><span data-stu-id="c06b7-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="c06b7-111">Die `REM` Anweisung muss die letzte Anweisung in der Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="c06b7-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="c06b7-112">Wenn Sie auf eine andere Anweisung folgt, muss die von `REM` dieser Anweisung durch ein Leerzeichen getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="c06b7-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="c06b7-113">Anstelle von können Sie ein einzelnes Anführungszeichen ( `'` ) verwenden `REM` .</span><span class="sxs-lookup"><span data-stu-id="c06b7-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="c06b7-114">Dies gilt unabhängig davon, ob Ihr Kommentar auf eine andere Anweisung in derselben Zeile folgt oder sich allein in einer Zeile befindet.</span><span class="sxs-lookup"><span data-stu-id="c06b7-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c06b7-115">Sie können eine `REM` Anweisung nicht mithilfe einer Zeilen Fortsetzungs Sequenz fortsetzen ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="c06b7-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="c06b7-116">Nachdem ein Kommentar begonnen hat, untersucht der Compiler die Zeichen nicht auf eine besondere Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="c06b7-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="c06b7-117">Verwenden Sie für einen mehrzeiligen Kommentar eine andere- `REM` Anweisung oder ein Kommentar Symbol ( `'` ) für jede Zeile.</span><span class="sxs-lookup"><span data-stu-id="c06b7-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c06b7-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c06b7-118">Example</span></span>  

 <span data-ttu-id="c06b7-119">Im folgenden Beispiel wird die- `REM` Anweisung veranschaulicht, die zum einschließen erklärender Hinweise in ein Programm verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c06b7-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="c06b7-120">Außerdem wird die Alternative zum Verwenden des einfachen Anführungs Zeichens ( `'` ) anstelle von angezeigt `REM` .</span><span class="sxs-lookup"><span data-stu-id="c06b7-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="c06b7-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c06b7-121">See also</span></span>

- [<span data-ttu-id="c06b7-122">Kommentare in Code</span><span class="sxs-lookup"><span data-stu-id="c06b7-122">Comments in Code</span></span>](../../programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="c06b7-123">Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="c06b7-123">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
