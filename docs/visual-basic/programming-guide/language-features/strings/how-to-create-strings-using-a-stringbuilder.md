---
title: 'Gewusst wie: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9def5da754d9075a8b498ac80e624caae5c97b96
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="3d1ed-102">Gewusst wie: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3d1ed-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="3d1ed-103">In diesem Beispiel erstellt eine lange Zeichenfolge aus vielen kleineren Zeichenfolgen, die mithilfe der <xref:System.Text.StringBuilder> Klasse.</span><span class="sxs-lookup"><span data-stu-id="3d1ed-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="3d1ed-104">Die <xref:System.Text.StringBuilder> Klasse ist effizienter als die `&=` Operator für viele Zeichenfolgen verketten.</span><span class="sxs-lookup"><span data-stu-id="3d1ed-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d1ed-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3d1ed-105">Example</span></span>  
 <span data-ttu-id="3d1ed-106">Das folgende Beispiel erstellt eine Instanz von der <xref:System.Text.StringBuilder> -Klasse, fügt Sie 1.000 Zeichenfolgen an diese Instanz und gibt die Zeichenfolgendarstellung.</span><span class="sxs-lookup"><span data-stu-id="3d1ed-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3d1ed-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d1ed-107">See Also</span></span>  
 [<span data-ttu-id="3d1ed-108">Verwenden der StringBuilder-Klasse</span><span class="sxs-lookup"><span data-stu-id="3d1ed-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)  
 [<span data-ttu-id="3d1ed-109">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="3d1ed-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="3d1ed-110">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="3d1ed-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="3d1ed-111">Erstellen neuer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="3d1ed-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="3d1ed-112">Bearbeiten von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="3d1ed-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)  
 [<span data-ttu-id="3d1ed-113">Zeichenfolgen-Beispiel</span><span class="sxs-lookup"><span data-stu-id="3d1ed-113">Strings Sample</span></span>](http://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02)
