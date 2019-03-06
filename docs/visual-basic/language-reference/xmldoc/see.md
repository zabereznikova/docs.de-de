---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: c26e818276eb4654fec77230372a0ae090952961
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474838"
---
# <a name="see-visual-basic"></a><span data-ttu-id="c786f-102">\<finden Sie unter > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c786f-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="c786f-103">Gibt einen Link zu einem anderen Member an.</span><span class="sxs-lookup"><span data-stu-id="c786f-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c786f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c786f-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c786f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c786f-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="c786f-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c786f-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="c786f-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c786f-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="c786f-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="c786f-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c786f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c786f-109">Remarks</span></span>  
 <span data-ttu-id="c786f-110">Verwenden der `<see>` Tag, um einen Link im Text angegeben.</span><span class="sxs-lookup"><span data-stu-id="c786f-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="c786f-111">Verwendung [ \<Seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) um Text anzugeben, die möglicherweise in einem Abschnitt "Siehe auch" angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c786f-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="c786f-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="c786f-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c786f-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c786f-113">Example</span></span>  
 <span data-ttu-id="c786f-114">Dieses Beispiel verwendet die `<see>` -Tag in die `UpdateRecord` Hinweise im Abschnitt zum Verweisen auf die `DoesRecordExist` Methode.</span><span class="sxs-lookup"><span data-stu-id="c786f-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="c786f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c786f-115">See also</span></span>
- [<span data-ttu-id="c786f-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="c786f-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
