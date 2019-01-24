---
title: Attribut &#39; &lt;Attributename&gt; &#39; kann nicht mehrmals angewendet werden
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 6609ce299799bc3c4b78d48478e99e4d4101dd72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565162"
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a><span data-ttu-id="29451-102">Attribut &#39; &lt;Attributename&gt; &#39; kann nicht mehrmals angewendet werden</span><span class="sxs-lookup"><span data-stu-id="29451-102">Attribute &#39;&lt;attributename&gt;&#39; cannot be applied multiple times</span></span>
<span data-ttu-id="29451-103">Das Attribut kann nur einmal angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="29451-103">The attribute can only be applied once.</span></span> <span data-ttu-id="29451-104">Die `AttributeUsage` Attribut bestimmt, ob ein Attribut mehr als einmal angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="29451-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="29451-105">**Fehler-ID:** BC30663</span><span class="sxs-lookup"><span data-stu-id="29451-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="29451-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="29451-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="29451-107">Stellen Sie sicher, dass das Attribut nur einmal angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="29451-107">Make sure the attribute is only applied once.</span></span>  
  
2.  <span data-ttu-id="29451-108">Wenn Sie benutzerdefinierte Attribute, die für Sie entwickelt haben verwenden werden, können Sie ändern die `AttributeUsage` Attribut, um die Verwendung von mehreren Attributen, wie Sie mit dem folgenden Beispiel zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="29451-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="29451-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29451-109">See also</span></span>
- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="29451-110">Erstellen benutzerdefinierter Attribute</span><span class="sxs-lookup"><span data-stu-id="29451-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="29451-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="29451-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
