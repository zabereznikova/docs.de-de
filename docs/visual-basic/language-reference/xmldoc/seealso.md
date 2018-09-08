---
title: '&lt;Seealso&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: a792bbea108bcdf33d430c47773466ef3dccdb0c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44182829"
---
# <a name="ltseealsogt-visual-basic"></a><span data-ttu-id="90eed-102">&lt;Seealso&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90eed-102">&lt;seealso&gt; (Visual Basic)</span></span>
<span data-ttu-id="90eed-103">Gibt einen Link, der im Abschnitt Siehe auch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="90eed-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90eed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90eed-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90eed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="90eed-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="90eed-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="90eed-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="90eed-107">Der Compiler überprüft, dass das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="90eed-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="90eed-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="90eed-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90eed-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90eed-109">Remarks</span></span>  
 <span data-ttu-id="90eed-110">Verwenden der `<seealso>` Tag, um den Text angeben, die in einem Abschnitt Siehe auch angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="90eed-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="90eed-111">Mit [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="90eed-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="90eed-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="90eed-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90eed-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90eed-113">Example</span></span>  
 <span data-ttu-id="90eed-114">Dieses Beispiel verwendet die `<seealso>` -Tag in die `DoesRecordExist` Hinweise im Abschnitt zum Verweisen auf die `UpdateRecord` Methode.</span><span class="sxs-lookup"><span data-stu-id="90eed-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="90eed-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90eed-115">See Also</span></span>  
 [<span data-ttu-id="90eed-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="90eed-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
