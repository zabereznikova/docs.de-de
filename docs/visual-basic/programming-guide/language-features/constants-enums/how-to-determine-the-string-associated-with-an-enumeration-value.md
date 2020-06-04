---
title: 'Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 525da9206472afefa9f85b49ceee0775cbd168c3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414465"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="030f2-102">Gewusst wie: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="030f2-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="030f2-103">Die <xref:System.Enum.GetValues%2A> -Methode und die- <xref:System.Enum.GetNames%2A> Methode ermöglichen es Ihnen, die mit Enumerationsmembern verknüpften Zeichen folgen und Werte</span><span class="sxs-lookup"><span data-stu-id="030f2-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="030f2-104">So bestimmen Sie die Zeichenfolge, die einer Enumeration zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="030f2-104">To determine the string associated with an enumeration</span></span>  
  
- <span data-ttu-id="030f2-105">Verwenden Sie die- <xref:System.Enum.GetNames%2A> Methode, um die den Enumerationsmembern zugeordneten Zeichen folgen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="030f2-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="030f2-106">In diesem Beispiel wird eine Enumeration deklariert, `flavorEnum` und dann wird die-Methode verwendet, <xref:System.Enum.GetNames%2A> um die den einzelnen Membern zugeordneten Zeichen folgen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="030f2-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="030f2-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="030f2-107">See also</span></span>

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="030f2-108">Gewusst wie: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="030f2-108">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="030f2-109">Vorgehensweise: Verweisen auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="030f2-109">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="030f2-110">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="030f2-110">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="030f2-111">Gewusst wie: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="030f2-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="030f2-112">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="030f2-112">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="030f2-113">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="030f2-113">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
