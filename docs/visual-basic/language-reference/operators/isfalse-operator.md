---
title: IsFalse-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 7c5ad5fa0b72370eeb19fbaced88807570467552
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370673"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="cc4c4-102">IsFalse-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc4c4-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="cc4c4-103">Bestimmt, ob ein Ausdruck ist `False` .</span><span class="sxs-lookup"><span data-stu-id="cc4c4-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="cc4c4-104">Sie können nicht `IsFalse` explizit in Ihrem Code aufzurufen, der Visual Basic Compiler kann es jedoch zum Generieren von Code aus `AndAlso` Klauseln verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc4c4-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="cc4c4-105">Wenn Sie eine Klasse oder Struktur definieren und dann eine Variable dieses Typs in einer- `AndAlso` Klausel verwenden, müssen Sie `IsFalse` für diese Klasse oder Struktur definieren.</span><span class="sxs-lookup"><span data-stu-id="cc4c4-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="cc4c4-106">Der Compiler betrachtet die `IsFalse` `IsTrue` Operatoren und als ein *übereinstimmendes Paar*.</span><span class="sxs-lookup"><span data-stu-id="cc4c4-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="cc4c4-107">Dies bedeutet, dass Sie, wenn Sie einen von Ihnen definieren, auch den anderen definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="cc4c4-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc4c4-108">Der `IsFalse` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="cc4c4-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="cc4c4-109">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="cc4c4-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="cc4c4-110">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="cc4c4-110">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc4c4-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc4c4-111">Example</span></span>  
 <span data-ttu-id="cc4c4-112">Im folgenden Codebeispiel wird die Gliederung einer-Struktur definiert, die Definitionen für die `IsFalse` `IsTrue` Operatoren und enthält.</span><span class="sxs-lookup"><span data-stu-id="cc4c4-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="cc4c4-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc4c4-113">See also</span></span>

- [<span data-ttu-id="cc4c4-114">IsTrue-Operator</span><span class="sxs-lookup"><span data-stu-id="cc4c4-114">IsTrue Operator</span></span>](istrue-operator.md)
- [<span data-ttu-id="cc4c4-115">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="cc4c4-115">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="cc4c4-116">AndAlso-Operator</span><span class="sxs-lookup"><span data-stu-id="cc4c4-116">AndAlso Operator</span></span>](andalso-operator.md)
