---
title: 'Gewusst wie: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: c396a4e2ebe973f5be65c3fab5f22cdedb29be1a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351130"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="ea224-102">Gewusst wie: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea224-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="ea224-103">Die Methoden <xref:System.Enum.GetValues%2A> und <xref:System.Enum.GetNames%2A> ermöglichen es Ihnen, die Zeichen folgen und Werte zu ermitteln, die mit Enumerationsmembern verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="ea224-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="ea224-104">So bestimmen Sie die Zeichenfolge, die einer Enumeration zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="ea224-104">To determine the string associated with an enumeration</span></span>  
  
- <span data-ttu-id="ea224-105">Verwenden Sie die <xref:System.Enum.GetNames%2A>-Methode, um die den Enumerationsmembern zugeordneten Zeichen folgen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ea224-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="ea224-106">In diesem Beispiel wird eine Enumeration deklariert, `flavorEnum`und dann die <xref:System.Enum.GetNames%2A>-Methode verwendet, um die den einzelnen Membern zugeordneten Zeichen folgen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea224-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ea224-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea224-107">See also</span></span>

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="ea224-108">Gewusst wie: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="ea224-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="ea224-109">Gewusst wie: Verweisen auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="ea224-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="ea224-110">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="ea224-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="ea224-111">Gewusst wie: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea224-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="ea224-112">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ea224-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="ea224-113">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ea224-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
