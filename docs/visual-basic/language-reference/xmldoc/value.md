---
title: '&lt;Wert&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: ef14836c438cf6a1de300270d9882c1e53e716ee
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855932"
---
# <a name="ltvaluegt-visual-basic"></a><span data-ttu-id="4a560-102">&lt;Wert&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a560-102">&lt;value&gt; (Visual Basic)</span></span>
<span data-ttu-id="4a560-103">Gibt die Beschreibung einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4a560-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a560-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a560-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a560-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a560-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="4a560-106">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4a560-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a560-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a560-107">Remarks</span></span>  
 <span data-ttu-id="4a560-108">Verwenden der `<value>` Tag, um eine Eigenschaft beschreiben.</span><span class="sxs-lookup"><span data-stu-id="4a560-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="4a560-109">Beachten Sie, dass wenn Sie eine Eigenschaft mit dem Code-Assistenten in der Entwicklungsumgebung von Visual Studio hinzufügen, wird es Hinzufügen einer [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) Tag für die neue Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4a560-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="4a560-110">Sie sollten dann manuell hinzufügen einer `<value>` Tag, um den Wert zu beschreiben, die die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="4a560-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="4a560-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="4a560-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a560-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4a560-112">Example</span></span>  
 <span data-ttu-id="4a560-113">Dieses Beispiel verwendet die `<value>` Tag beschrieben, welchen Wert die `Counter` Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="4a560-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4a560-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a560-114">See Also</span></span>  
 [<span data-ttu-id="4a560-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="4a560-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
