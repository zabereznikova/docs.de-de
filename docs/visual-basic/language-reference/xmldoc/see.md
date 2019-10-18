---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: e3ae5fb63540e47e5b8da2e2d60d5bd736e019d7
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524654"
---
# <a name="see-visual-basic"></a><span data-ttu-id="8f1f1-102">\<see > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f1f1-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="8f1f1-103">Gibt einen Link zu einem anderen Element an.</span><span class="sxs-lookup"><span data-stu-id="8f1f1-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f1f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f1f1-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f1f1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f1f1-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="8f1f1-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f1f1-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="8f1f1-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="8f1f1-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="8f1f1-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="8f1f1-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f1f1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f1f1-109">Remarks</span></span>  
 <span data-ttu-id="8f1f1-110">Verwenden Sie das `<see>`-Tag, um eine Verknüpfung innerhalb von Text anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8f1f1-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="8f1f1-111">Verwenden Sie [\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) , um Text anzugeben, der möglicherweise im Abschnitt "Siehe auch" angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f1f1-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="8f1f1-112">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8f1f1-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f1f1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f1f1-113">Example</span></span>  
 <span data-ttu-id="8f1f1-114">In diesem Beispiel wird das `<see>`-Tag im Abschnitt `UpdateRecord` Hinweise verwendet, um auf die `DoesRecordExist`-Methode zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="8f1f1-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="8f1f1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f1f1-115">See also</span></span>

- [<span data-ttu-id="8f1f1-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="8f1f1-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
