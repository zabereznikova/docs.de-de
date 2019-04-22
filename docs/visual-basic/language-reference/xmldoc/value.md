---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 2938d485bf6c547c792431b93fc8959c9c36befa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821412"
---
# <a name="value-visual-basic"></a><span data-ttu-id="4edbc-102">\<Wert > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4edbc-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="4edbc-103">Gibt die Beschreibung einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4edbc-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4edbc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4edbc-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4edbc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4edbc-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="4edbc-106">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4edbc-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4edbc-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4edbc-107">Remarks</span></span>  
 <span data-ttu-id="4edbc-108">Verwenden der `<value>` Tag, um eine Eigenschaft beschreiben.</span><span class="sxs-lookup"><span data-stu-id="4edbc-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="4edbc-109">Beachten Sie, dass wenn Sie eine Eigenschaft mit dem Code-Assistenten in der Entwicklungsumgebung von Visual Studio hinzufügen, wird es Hinzufügen einer [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) Tag für die neue Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4edbc-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="4edbc-110">Sie sollten dann manuell hinzufügen einer `<value>` Tag, um den Wert zu beschreiben, die die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="4edbc-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="4edbc-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="4edbc-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4edbc-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4edbc-112">Example</span></span>  
 <span data-ttu-id="4edbc-113">Dieses Beispiel verwendet die `<value>` Tag beschrieben, welchen Wert die `Counter` Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="4edbc-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4edbc-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4edbc-114">See also</span></span>

- [<span data-ttu-id="4edbc-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="4edbc-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
