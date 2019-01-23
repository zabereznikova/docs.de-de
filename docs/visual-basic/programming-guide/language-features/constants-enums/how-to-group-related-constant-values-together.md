---
title: 'Vorgehensweise: Gruppieren Sie verwandter konstanter Werte zusammen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 04697092534daa6f83a29e69dcdc509644fa6147
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558682"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="bec74-102">Vorgehensweise: Gruppieren Sie verwandter konstanter Werte zusammen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bec74-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="bec74-103">Eine Enumeration ist die beste Methode zum Gruppieren verwandter Konstanten.</span><span class="sxs-lookup"><span data-stu-id="bec74-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="bec74-104">Sie erstellen eine Enumeration mit den `Enum` Anweisung im Abschnitt zu Deklarationen einer Klasse oder ein Modul.</span><span class="sxs-lookup"><span data-stu-id="bec74-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="bec74-105">Weitere Informationen finden Sie unter [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="bec74-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="bec74-106">Gruppe verwandter konstanter Werte</span><span class="sxs-lookup"><span data-stu-id="bec74-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="bec74-107">Schreiben Sie eine Deklaration, die eine Ebene, enthält die `Enum` -Schlüsselwort und einen gültigen Namen.</span><span class="sxs-lookup"><span data-stu-id="bec74-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="bec74-108">In diesem Beispiel wird die `Private` Enumeration `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="bec74-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_1.vb)]  
  
2.  <span data-ttu-id="bec74-109">Definieren der Konstanten in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="bec74-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="bec74-110">In diesem Beispiel wird die `Public` Enumeration `temperatureValues` und ihre Werte zuordnet.</span><span class="sxs-lookup"><span data-stu-id="bec74-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bec74-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bec74-111">See also</span></span>
- [<span data-ttu-id="bec74-112">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="bec74-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="bec74-113">Vorgehensweise: Finden Sie in einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="bec74-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="bec74-114">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="bec74-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="bec74-115">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="bec74-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="bec74-116">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="bec74-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="bec74-117">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="bec74-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
