---
title: 'Gewusst wie: Erstellen von Zeichenfolgen mit einem StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: c41db584df83782dab99b90043045aa2cabcb6ff
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645327"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="4b3ab-102">Gewusst wie: Erstellen von Zeichenfolgen mit einem StringBuilder in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b3ab-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="4b3ab-103">In diesem Beispiel wird eine lange Zeichenfolge <xref:System.Text.StringBuilder> aus vielen kleineren Zeichenfolgen mithilfe der Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="4b3ab-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="4b3ab-104">Die <xref:System.Text.StringBuilder> Klasse ist effizienter `&=` als der Operator, um viele Zeichenfolgen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="4b3ab-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="4b3ab-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b3ab-105">Example</span></span>

<span data-ttu-id="4b3ab-106">Im folgenden Beispiel wird <xref:System.Text.StringBuilder> eine Instanz der Klasse erstellt, 1.000 Zeichenfolgen an diese Instanz angehängt und dann ihre Zeichenfolgendarstellung zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="4b3ab-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="4b3ab-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b3ab-107">See also</span></span>

- [<span data-ttu-id="4b3ab-108">Verwenden der StringBuilder-Klasse</span><span class="sxs-lookup"><span data-stu-id="4b3ab-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="4b3ab-109">&= Operator</span><span class="sxs-lookup"><span data-stu-id="4b3ab-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="4b3ab-110">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="4b3ab-110">Strings</span></span>](index.md)
- [<span data-ttu-id="4b3ab-111">Erstellen neuer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="4b3ab-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="4b3ab-112">Bearbeiten von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="4b3ab-112">Manipulating Strings</span></span>](../../../../standard/base-types/best-practices-strings.md)
