---
title: '&lt;finden Sie unter&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 78311651593d3d4a47c723f64a9a74d4660f7c90
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43254061"
---
# <a name="ltseegt-visual-basic"></a><span data-ttu-id="3b6c1-102">&lt;finden Sie unter&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b6c1-102">&lt;see&gt; (Visual Basic)</span></span>
<span data-ttu-id="3b6c1-103">Gibt einen Link zu einem anderen Member an.</span><span class="sxs-lookup"><span data-stu-id="3b6c1-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b6c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b6c1-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b6c1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3b6c1-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="3b6c1-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3b6c1-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="3b6c1-107">Der Compiler überprüft, dass das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="3b6c1-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="3b6c1-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="3b6c1-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b6c1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3b6c1-109">Remarks</span></span>  
 <span data-ttu-id="3b6c1-110">Verwenden der `<see>` Tag, um einen Link im Text angegeben.</span><span class="sxs-lookup"><span data-stu-id="3b6c1-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="3b6c1-111">Verwendung [ \<Seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) um Text anzugeben, die möglicherweise in einem Abschnitt "Siehe auch" angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3b6c1-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="3b6c1-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="3b6c1-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b6c1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b6c1-113">Example</span></span>  
 <span data-ttu-id="3b6c1-114">Dieses Beispiel verwendet die `<see>` -Tag in die `UpdateRecord` Hinweise im Abschnitt zum Verweisen auf die `DoesRecordExist` Methode.</span><span class="sxs-lookup"><span data-stu-id="3b6c1-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3b6c1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b6c1-115">See Also</span></span>  
 [<span data-ttu-id="3b6c1-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="3b6c1-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
