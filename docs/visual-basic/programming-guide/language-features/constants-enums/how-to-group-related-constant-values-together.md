---
title: 'Vorgehensweise: Gruppieren verwandter konstanter Werte'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 0f694aee722e8ce31f663ec9fe52a09a2eb2a958
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058728"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="aa285-102">Gewusst wie: Gruppieren verwandter konstanter Werte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa285-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>

<span data-ttu-id="aa285-103">Eine Enumeration ist die beste Möglichkeit, Verwandte Konstanten zusammen zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="aa285-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="aa285-104">Sie erstellen eine Enumeration mit der- `Enum` Anweisung im Deklarations Abschnitt einer Klasse oder eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="aa285-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="aa285-105">Weitere Informationen finden Sie unter Gewusst [wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="aa285-105">For more information, see [How to: Declare an Enumeration](how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="aa285-106">Gruppieren verwandter konstanter Werte</span><span class="sxs-lookup"><span data-stu-id="aa285-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="aa285-107">Schreiben Sie eine Deklaration, die eine Code Zugriffsebene, das `Enum` Schlüsselwort und einen gültigen Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="aa285-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="aa285-108">In diesem Beispiel wird die- `Private` Enumeration erstellt `temperatureValues` .</span><span class="sxs-lookup"><span data-stu-id="aa285-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="aa285-109">Definieren Sie die Konstanten in der-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="aa285-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="aa285-110">In diesem Beispiel wird die `Public` -Enumeration erstellt, `temperatureValues` und ihre Werte werden zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="aa285-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="aa285-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa285-111">See also</span></span>

- [<span data-ttu-id="aa285-112">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="aa285-112">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="aa285-113">Vorgehensweise: Verweisen auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="aa285-113">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="aa285-114">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="aa285-114">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="aa285-115">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="aa285-115">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="aa285-116">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="aa285-116">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="aa285-117">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="aa285-117">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
