---
title: Das Attribut "<attributename>" kann nicht mehrmals angewendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 62e84d174e4e218472eda9b7c08ed677e0140438
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278706"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="6d580-102">Attribut "\<Attributname >' kann nicht mehrmals angewendet werden</span><span class="sxs-lookup"><span data-stu-id="6d580-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>
<span data-ttu-id="6d580-103">Das Attribut kann nur einmal angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6d580-103">The attribute can only be applied once.</span></span> <span data-ttu-id="6d580-104">Die `AttributeUsage` Attribut bestimmt, ob ein Attribut mehr als einmal angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6d580-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="6d580-105">**Fehler-ID:** BC30663</span><span class="sxs-lookup"><span data-stu-id="6d580-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6d580-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6d580-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="6d580-107">Stellen Sie sicher, dass das Attribut nur einmal angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6d580-107">Make sure the attribute is only applied once.</span></span>  
  
2.  <span data-ttu-id="6d580-108">Wenn Sie benutzerdefinierte Attribute, die für Sie entwickelt haben verwenden werden, können Sie ändern die `AttributeUsage` Attribut, um die Verwendung von mehreren Attributen, wie Sie mit dem folgenden Beispiel zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6d580-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d580-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d580-109">See also</span></span>
- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="6d580-110">Erstellen benutzerdefinierter Attribute</span><span class="sxs-lookup"><span data-stu-id="6d580-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="6d580-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="6d580-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
