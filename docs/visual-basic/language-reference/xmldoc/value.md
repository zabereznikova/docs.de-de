---
title: '&lt;Wert&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: f33a4ec32b45d8996bd39f0cc49097b5fd9252e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602457"
---
# <a name="ltvaluegt-visual-basic"></a><span data-ttu-id="e0dc9-102">&lt;Wert&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0dc9-102">&lt;value&gt; (Visual Basic)</span></span>
<span data-ttu-id="e0dc9-103">Gibt die Beschreibung einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e0dc9-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0dc9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0dc9-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0dc9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0dc9-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="e0dc9-106">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e0dc9-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0dc9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0dc9-107">Remarks</span></span>  
 <span data-ttu-id="e0dc9-108">Verwenden der `<value>` -Tag, um eine Eigenschaft zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="e0dc9-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="e0dc9-109">Beachten Sie, dass beim Hinzufügen einer Eigenschaft mit dem Code-Assistenten in der Visual Studio-Entwicklungsumgebung hinzufügen wird ein [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) Tag für die neue Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e0dc9-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="e0dc9-110">Sie sollten dann manuell hinzufügen einer `<value>` -Tag, um den Wert zu beschreiben, die die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="e0dc9-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="e0dc9-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="e0dc9-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0dc9-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0dc9-112">Example</span></span>  
 <span data-ttu-id="e0dc9-113">Dieses Beispiel verwendet die `<value>` Tag beschrieben, welchen Wert die `Counter` Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="e0dc9-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e0dc9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0dc9-114">See Also</span></span>  
 [<span data-ttu-id="e0dc9-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="e0dc9-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
