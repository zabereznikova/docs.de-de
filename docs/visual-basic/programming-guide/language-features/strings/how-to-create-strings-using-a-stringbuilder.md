---
title: 'Vorgehensweise: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 84f0f41cf8ee23466d47dae3b1068c3bc5334072
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528445"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="c7ff0-102">Vorgehensweise: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7ff0-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="c7ff0-103">In diesem Beispiel erstellt eine lange Zeichenfolge aus vielen kleineren Zeichenfolgen, die mit der <xref:System.Text.StringBuilder> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c7ff0-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="c7ff0-104">Die <xref:System.Text.StringBuilder> Klasse ist effizienter als die `&=` Operators für viele Zeichenfolgen verketten.</span><span class="sxs-lookup"><span data-stu-id="c7ff0-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7ff0-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7ff0-105">Example</span></span>  
 <span data-ttu-id="c7ff0-106">Das folgende Beispiel erstellt eine Instanz der <xref:System.Text.StringBuilder> -Klasse fügt 1.000 Zeichenfolgen an diese Instanz an, und gibt anschließend die Zeichenfolgendarstellung.</span><span class="sxs-lookup"><span data-stu-id="c7ff0-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c7ff0-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7ff0-107">See also</span></span>
- [<span data-ttu-id="c7ff0-108">Verwenden der StringBuilder-Klasse</span><span class="sxs-lookup"><span data-stu-id="c7ff0-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="c7ff0-109">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="c7ff0-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="c7ff0-110">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="c7ff0-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="c7ff0-111">Erstellen neuer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="c7ff0-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="c7ff0-112">Bearbeiten von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="c7ff0-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
- <span data-ttu-id="c7ff0-113">[Strings-Beispiel](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c7ff0-113">[Strings Sample](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span></span>
