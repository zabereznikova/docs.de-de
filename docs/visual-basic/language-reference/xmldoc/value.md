---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 2938d485bf6c547c792431b93fc8959c9c36befa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940737"
---
# <a name="value-visual-basic"></a><span data-ttu-id="9c628-102">\<Wert > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c628-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="9c628-103">Gibt die Beschreibung einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9c628-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c628-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c628-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c628-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c628-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="9c628-106">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9c628-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c628-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c628-107">Remarks</span></span>  
 <span data-ttu-id="9c628-108">Verwenden der `<value>` Tag, um eine Eigenschaft beschreiben.</span><span class="sxs-lookup"><span data-stu-id="9c628-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="9c628-109">Beachten Sie, dass wenn Sie eine Eigenschaft mit dem Code-Assistenten in der Entwicklungsumgebung von Visual Studio hinzufügen, wird es Hinzufügen einer [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) Tag für die neue Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9c628-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="9c628-110">Sie sollten dann manuell hinzufügen einer `<value>` Tag, um den Wert zu beschreiben, die die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="9c628-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="9c628-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="9c628-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c628-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c628-112">Example</span></span>  
 <span data-ttu-id="9c628-113">Dieses Beispiel verwendet die `<value>` Tag beschrieben, welchen Wert die `Counter` Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="9c628-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9c628-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c628-114">See also</span></span>

- [<span data-ttu-id="9c628-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="9c628-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
