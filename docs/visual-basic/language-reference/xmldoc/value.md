---
title: '&lt;Wert&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 92c8c2ac7b95e97b37c907e3837bc90dac384b33
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558942"
---
# <a name="ltvaluegt-visual-basic"></a><span data-ttu-id="8d122-102">&lt;Wert&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d122-102">&lt;value&gt; (Visual Basic)</span></span>
<span data-ttu-id="8d122-103">Gibt die Beschreibung einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8d122-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d122-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d122-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d122-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8d122-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="8d122-106">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8d122-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d122-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d122-107">Remarks</span></span>  
 <span data-ttu-id="8d122-108">Verwenden der `<value>` Tag, um eine Eigenschaft beschreiben.</span><span class="sxs-lookup"><span data-stu-id="8d122-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="8d122-109">Beachten Sie, dass wenn Sie eine Eigenschaft mit dem Code-Assistenten in der Entwicklungsumgebung von Visual Studio hinzufügen, wird es Hinzufügen einer [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) Tag für die neue Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8d122-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="8d122-110">Sie sollten dann manuell hinzufügen einer `<value>` Tag, um den Wert zu beschreiben, die die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="8d122-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="8d122-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="8d122-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d122-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d122-112">Example</span></span>  
 <span data-ttu-id="8d122-113">Dieses Beispiel verwendet die `<value>` Tag beschrieben, welchen Wert die `Counter` Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="8d122-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8d122-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d122-114">See also</span></span>
- [<span data-ttu-id="8d122-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="8d122-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
