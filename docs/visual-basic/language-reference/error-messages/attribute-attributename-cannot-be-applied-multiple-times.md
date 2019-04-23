---
title: Das Attribut "<attributename>" kann nicht mehrmals angewendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: da4a766e2617308cb33b9673a88db9e7a954152a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304297"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="ffd62-102">Attribut "\<Attributname >' kann nicht mehrmals angewendet werden</span><span class="sxs-lookup"><span data-stu-id="ffd62-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>
<span data-ttu-id="ffd62-103">Das Attribut kann nur einmal angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ffd62-103">The attribute can only be applied once.</span></span> <span data-ttu-id="ffd62-104">Die `AttributeUsage` Attribut bestimmt, ob ein Attribut mehr als einmal angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ffd62-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="ffd62-105">**Fehler-ID:** BC30663</span><span class="sxs-lookup"><span data-stu-id="ffd62-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ffd62-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ffd62-106">To correct this error</span></span>  
  
1. <span data-ttu-id="ffd62-107">Stellen Sie sicher, dass das Attribut nur einmal angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ffd62-107">Make sure the attribute is only applied once.</span></span>  
  
2. <span data-ttu-id="ffd62-108">Wenn Sie benutzerdefinierte Attribute, die für Sie entwickelt haben verwenden werden, können Sie ändern die `AttributeUsage` Attribut, um die Verwendung von mehreren Attributen, wie Sie mit dem folgenden Beispiel zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ffd62-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffd62-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffd62-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="ffd62-110">Erstellen benutzerdefinierter Attribute</span><span class="sxs-lookup"><span data-stu-id="ffd62-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="ffd62-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="ffd62-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
