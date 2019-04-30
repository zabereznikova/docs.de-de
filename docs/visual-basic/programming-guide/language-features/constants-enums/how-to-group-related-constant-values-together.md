---
title: 'Vorgehensweise: Gruppieren Sie verwandter konstanter Werte zusammen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: a4f74e48cfdd5c0bc0f745d0f32eb39442f5bd83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906762"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="d0250-102">Vorgehensweise: Gruppieren Sie verwandter konstanter Werte zusammen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0250-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="d0250-103">Eine Enumeration ist die beste Methode zum Gruppieren verwandter Konstanten.</span><span class="sxs-lookup"><span data-stu-id="d0250-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="d0250-104">Sie erstellen eine Enumeration mit den `Enum` Anweisung im Abschnitt zu Deklarationen einer Klasse oder ein Modul.</span><span class="sxs-lookup"><span data-stu-id="d0250-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="d0250-105">Weitere Informationen finden Sie unter [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="d0250-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="d0250-106">Gruppe verwandter konstanter Werte</span><span class="sxs-lookup"><span data-stu-id="d0250-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="d0250-107">Schreiben Sie eine Deklaration, die eine Ebene, enthält die `Enum` -Schlüsselwort und einen gültigen Namen.</span><span class="sxs-lookup"><span data-stu-id="d0250-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="d0250-108">In diesem Beispiel wird die `Private` Enumeration `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="d0250-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="d0250-109">Definieren der Konstanten in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="d0250-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="d0250-110">In diesem Beispiel wird die `Public` Enumeration `temperatureValues` und ihre Werte zuordnet.</span><span class="sxs-lookup"><span data-stu-id="d0250-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d0250-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0250-111">See also</span></span>

- [<span data-ttu-id="d0250-112">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="d0250-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="d0250-113">Vorgehensweise: Finden Sie in einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="d0250-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="d0250-114">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d0250-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="d0250-115">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="d0250-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="d0250-116">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="d0250-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="d0250-117">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d0250-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
