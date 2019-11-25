---
title: Das Attribut "<attributename>" kann nicht mehrmals angewendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: f2f4dc428a247275f9919c4a8b6e6944a558eef0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968225"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="a79a8-102">Das Attribut '\<AttributeName > ' kann nicht mehrmals angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a79a8-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>

<span data-ttu-id="a79a8-103">Das-Attribut kann nur einmal angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a79a8-103">The attribute can only be applied once.</span></span> <span data-ttu-id="a79a8-104">Das `AttributeUsage`-Attribut bestimmt, ob ein Attribut mehrmals angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a79a8-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="a79a8-105">**Fehler-ID:** BC30663</span><span class="sxs-lookup"><span data-stu-id="a79a8-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a79a8-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a79a8-106">To correct this error</span></span>  
  
1. <span data-ttu-id="a79a8-107">Stellen Sie sicher, dass das-Attribut nur einmal angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a79a8-107">Make sure the attribute is only applied once.</span></span>  
  
2. <span data-ttu-id="a79a8-108">Wenn Sie benutzerdefinierte Attribute verwenden, die Sie entwickelt haben, sollten Sie das `AttributeUsage` Attribut ändern, um die Verwendung mehrerer Attribute zuzulassen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a79a8-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a79a8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a79a8-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="a79a8-110">Erstellen benutzerdefinierter Attribute</span><span class="sxs-lookup"><span data-stu-id="a79a8-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="a79a8-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="a79a8-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
