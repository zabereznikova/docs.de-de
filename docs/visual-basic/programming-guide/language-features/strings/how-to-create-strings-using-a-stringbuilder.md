---
title: 'Gewusst wie: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 49f3271d41e9e858c6ecafe1dde5330ebff767f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647731"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="5a730-102">Gewusst wie: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a730-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="5a730-103">In diesem Beispiel erstellt eine lange Zeichenfolge aus vielen kleineren Zeichenfolgen, die mithilfe der <xref:System.Text.StringBuilder> Klasse.</span><span class="sxs-lookup"><span data-stu-id="5a730-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="5a730-104">Die <xref:System.Text.StringBuilder> Klasse ist effizienter als die `&=` Operator für viele Zeichenfolgen verketten.</span><span class="sxs-lookup"><span data-stu-id="5a730-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a730-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a730-105">Example</span></span>  
 <span data-ttu-id="5a730-106">Das folgende Beispiel erstellt eine Instanz von der <xref:System.Text.StringBuilder> -Klasse, fügt Sie 1.000 Zeichenfolgen an diese Instanz und gibt die Zeichenfolgendarstellung.</span><span class="sxs-lookup"><span data-stu-id="5a730-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5a730-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a730-107">See Also</span></span>  
 [<span data-ttu-id="5a730-108">Verwenden der StringBuilder-Klasse</span><span class="sxs-lookup"><span data-stu-id="5a730-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)  
 [<span data-ttu-id="5a730-109">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="5a730-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="5a730-110">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="5a730-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="5a730-111">Erstellen neuer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="5a730-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="5a730-112">Bearbeiten von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="5a730-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)  
 <span data-ttu-id="5a730-113">[Zeichenfolgen-Beispiel](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5a730-113">[Strings Sample](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span></span>
