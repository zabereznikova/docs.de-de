---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 516ff6ba534478d066b8ca06baee46bdd4b35265
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524601"
---
# <a name="value-visual-basic"></a><span data-ttu-id="e6df2-102">\<value > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6df2-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="e6df2-103">Gibt die Beschreibung einer Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="e6df2-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6df2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6df2-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6df2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6df2-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="e6df2-106">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e6df2-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6df2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6df2-107">Remarks</span></span>  
 <span data-ttu-id="e6df2-108">Verwenden Sie das `<value>`-Tag, um eine Eigenschaft zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="e6df2-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="e6df2-109">Beachten Sie, dass beim Hinzufügen einer Eigenschaft mithilfe des Code-Assistenten in der Visual Studio-Entwicklungsumgebung eine [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) -Tag für die neue Eigenschaft hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e6df2-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="e6df2-110">Sie sollten dann manuell ein `<value>`-Tag hinzufügen, um den Wert zu beschreiben, den die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="e6df2-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="e6df2-111">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e6df2-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6df2-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6df2-112">Example</span></span>  
 <span data-ttu-id="e6df2-113">In diesem Beispiel wird das `<value>`-Tag verwendet, um den Wert zu beschreiben, den die `Counter` Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="e6df2-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e6df2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6df2-114">See also</span></span>

- [<span data-ttu-id="e6df2-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="e6df2-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
