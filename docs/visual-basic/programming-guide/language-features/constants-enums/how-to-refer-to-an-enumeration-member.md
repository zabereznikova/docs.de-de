---
title: 'Vorgehensweise: Verweisen auf einen Enumerationsmember'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: d1b239e7d6be3ebf1e64d6589a4cc14dce8946f5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095667"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="d3230-102">Gewusst wie: Verweisen auf einen Enumerationsmember (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3230-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>

<span data-ttu-id="d3230-103">Enumerationen stellen eine bequeme Möglichkeit zum Arbeiten mit Sätzen verwandter Konstanten und zum Zuordnen konstanter Werte zu Namen dar.</span><span class="sxs-lookup"><span data-stu-id="d3230-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="d3230-104">Sie können zum Beispiel eine Enumeration für einen Satz von Integerkonstanten deklarieren, denen die Tage der Woche zugewiesen sind, und dann in Ihrem Code die Namen der Wochentage statt deren Integerwerte verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3230-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="d3230-105">Sie können mit der-Anweisung vermeiden, voll qualifizierte Namen zu verwenden `Imports` .</span><span class="sxs-lookup"><span data-stu-id="d3230-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="d3230-106">Weitere Informationen finden Sie unter [Enumerationen und namens Qualifizierung](enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="d3230-106">For more information, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="d3230-107">So verweisen Sie auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="d3230-107">To refer to an enumeration member</span></span>  
  
- <span data-ttu-id="d3230-108">Qualifizieren Sie den Elementnamen mit der-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="d3230-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="d3230-109">Im folgenden Beispiel wird der-Variablen beispielsweise der- `Saturday` Member der- `FirstDayOfWeek` Enumeration zugewiesen `DayValue` .</span><span class="sxs-lookup"><span data-stu-id="d3230-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="d3230-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3230-110">See also</span></span>

- [<span data-ttu-id="d3230-111">Gewusst wie: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="d3230-111">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="d3230-112">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="d3230-112">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="d3230-113">Gewusst wie: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3230-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="d3230-114">Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d3230-114">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="d3230-115">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d3230-115">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
