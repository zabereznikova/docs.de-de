---
title: Das Attribut "<attributename>" kann nicht mehrmals angewendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 14145f165adf5ccd20298a70ca5596488b488b0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409958"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="b6fa4-102">Das Attribut "\<attributename>" kann nicht mehrmals angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b6fa4-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>

<span data-ttu-id="b6fa4-103">Das-Attribut kann nur einmal angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b6fa4-103">The attribute can only be applied once.</span></span> <span data-ttu-id="b6fa4-104">Das- `AttributeUsage` Attribut bestimmt, ob ein Attribut mehrmals angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b6fa4-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="b6fa4-105">**Fehler-ID:** BC30663</span><span class="sxs-lookup"><span data-stu-id="b6fa4-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b6fa4-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b6fa4-106">To correct this error</span></span>  
  
1. <span data-ttu-id="b6fa4-107">Stellen Sie sicher, dass das-Attribut nur einmal angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b6fa4-107">Make sure the attribute is only applied once.</span></span>  
  
2. <span data-ttu-id="b6fa4-108">Wenn Sie von Ihnen entwickelte benutzerdefinierte Attribute verwenden, sollten Sie `AttributeUsage` das-Attribut ändern, um die Verwendung mehrerer Attribute zuzulassen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b6fa4-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6fa4-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6fa4-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="b6fa4-110">Erstellen benutzerdefinierter Attribute</span><span class="sxs-lookup"><span data-stu-id="b6fa4-110">Creating Custom Attributes</span></span>](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="b6fa4-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="b6fa4-111">AttributeUsage</span></span>](../../programming-guide/concepts/attributes/attributeusage.md)
