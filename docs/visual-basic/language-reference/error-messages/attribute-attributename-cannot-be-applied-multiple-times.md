---
title: Attribut &#39; &lt;Attributename&gt; &#39; kann nicht mehrmals angewendet werden
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: df97a4e391406661db98eb1c958c0e12e45b6c49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584858"
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a><span data-ttu-id="92869-102">Attribut &#39; &lt;Attributename&gt; &#39; kann nicht mehrmals angewendet werden</span><span class="sxs-lookup"><span data-stu-id="92869-102">Attribute &#39;&lt;attributename&gt;&#39; cannot be applied multiple times</span></span>
<span data-ttu-id="92869-103">Das Attribut kann nur einmal angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="92869-103">The attribute can only be applied once.</span></span> <span data-ttu-id="92869-104">Die `AttributeUsage` Attribut ermittelt, ob ein Attribut mehr als einmal angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="92869-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="92869-105">**Fehler-ID:** BC30663</span><span class="sxs-lookup"><span data-stu-id="92869-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="92869-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="92869-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="92869-107">Stellen Sie sicher, dass das Attribut nur einmal angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="92869-107">Make sure the attribute is only applied once.</span></span>  
  
2.  <span data-ttu-id="92869-108">Wenn Sie benutzerdefinierte Attribute Sie entwickelt haben verwenden, können Sie ändern die `AttributeUsage` Attribut, um mehreren Attributen, wie anhand des folgenden Beispiels zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="92869-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="92869-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92869-109">See Also</span></span>  
 <xref:System.AttributeUsageAttribute>  
 [<span data-ttu-id="92869-110">Erstellen benutzerdefinierter Attribute</span><span class="sxs-lookup"><span data-stu-id="92869-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="92869-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="92869-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
