---
title: 'Vorgehensweise: Bestimmen der Zeichenfolge, die eine Enumerationswert (Visual Basic) zugeordnet sind'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 92d2e9918429c9cf408f288f832e4615b95ad423
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690188"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="105fc-102">Vorgehensweise: Bestimmen der Zeichenfolge, die eine Enumerationswert (Visual Basic) zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="105fc-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="105fc-103">Die <xref:System.Enum.GetValues%2A> und <xref:System.Enum.GetNames%2A> Methoden ermöglichen es Ihnen, um zu bestimmen, die Zeichenfolgen und Enumerationsmember zugeordnete Werte.</span><span class="sxs-lookup"><span data-stu-id="105fc-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="105fc-104">Um zu bestimmen, die eine Enumeration zugeordnete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="105fc-104">To determine the string associated with an enumeration</span></span>  
  
-   <span data-ttu-id="105fc-105">Verwenden der <xref:System.Enum.GetNames%2A> Methode, um die Member der Enumeration zugeordneten Zeichenfolgen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="105fc-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="105fc-106">Das folgende Beispiel deklariert eine Enumeration, `flavorEnum`, verwendet dann die <xref:System.Enum.GetNames%2A> Methode zum Anzeigen der Zeichenfolgen, die jedes Element zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="105fc-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="105fc-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="105fc-107">See also</span></span>
- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="105fc-108">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="105fc-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="105fc-109">Vorgehensweise: Finden Sie in einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="105fc-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="105fc-110">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="105fc-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="105fc-111">Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="105fc-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="105fc-112">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="105fc-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="105fc-113">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="105fc-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
