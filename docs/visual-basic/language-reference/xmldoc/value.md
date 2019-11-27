---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 240c2131179420834e6dade729ee631c0d7811a4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352177"
---
# <a name="value-visual-basic"></a><span data-ttu-id="1c6f9-101">\<Wert > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c6f9-101">\<value> (Visual Basic)</span></span>
<span data-ttu-id="1c6f9-102">Gibt die Beschreibung einer Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="1c6f9-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c6f9-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c6f9-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c6f9-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c6f9-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="1c6f9-105">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1c6f9-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c6f9-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c6f9-106">Remarks</span></span>  
 <span data-ttu-id="1c6f9-107">Verwenden Sie das `<value>`-Tag, um eine Eigenschaft zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="1c6f9-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="1c6f9-108">Beachten Sie, dass beim Hinzufügen einer Eigenschaft mithilfe des Code-Assistenten in der Visual Studio-Entwicklungsumgebung eine [\<Zusammenfassungs >](../../../visual-basic/language-reference/xmldoc/summary.md) -Tags für die neue Eigenschaft hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1c6f9-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="1c6f9-109">Sie sollten dann manuell ein `<value>`-Tag hinzufügen, um den Wert zu beschreiben, den die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="1c6f9-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="1c6f9-110">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1c6f9-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c6f9-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c6f9-111">Example</span></span>  
 <span data-ttu-id="1c6f9-112">In diesem Beispiel wird das `<value>`-Tag verwendet, um den Wert zu beschreiben, den die `Counter` Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="1c6f9-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1c6f9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c6f9-113">See also</span></span>

- [<span data-ttu-id="1c6f9-114">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="1c6f9-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
