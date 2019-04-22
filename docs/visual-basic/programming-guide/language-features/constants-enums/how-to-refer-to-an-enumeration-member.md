---
title: 'Vorgehensweise: Finden Sie in einen Enumerationsmember (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: e9ea359d58dfa11f7bba7fec3d31955e18d24953
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813976"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="4b6d0-102">Vorgehensweise: Finden Sie in einen Enumerationsmember (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b6d0-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="4b6d0-103">Enumerationen bieten eine bequeme Möglichkeit, um mit Sätzen verknüpfter Konstanten zu arbeiten und Konstante Werten Namen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="4b6d0-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="4b6d0-104">Sie können zum Beispiel eine Enumeration für einen Satz von Integerkonstanten deklarieren, denen die Tage der Woche zugewiesen sind, und dann in Ihrem Code die Namen der Wochentage statt deren Integerwerte verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b6d0-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="4b6d0-105">Sie können vermeiden, verwenden den vollqualifizierten Namen der `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4b6d0-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="4b6d0-106">Weitere Informationen finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="4b6d0-106">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="4b6d0-107">Zum Verweisen auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="4b6d0-107">To refer to an enumeration member</span></span>  
  
-   <span data-ttu-id="4b6d0-108">Qualifizieren Sie den Namen des Members mit der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4b6d0-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="4b6d0-109">Im folgende Beispiel weist z. B. die `Saturday` Mitglied der `FirstDayOfWeek` Enumeration, um die Variable `DayValue`.</span><span class="sxs-lookup"><span data-stu-id="4b6d0-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="4b6d0-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b6d0-110">See also</span></span>

- [<span data-ttu-id="4b6d0-111">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="4b6d0-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="4b6d0-112">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="4b6d0-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="4b6d0-113">Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b6d0-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="4b6d0-114">Vorgehensweise: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b6d0-114">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="4b6d0-115">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="4b6d0-115">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
