---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 3c149b8ff60bcc2aba06856ad95f461fb18da4b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352227"
---
# <a name="see-visual-basic"></a><span data-ttu-id="5d723-101">\<siehe > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d723-101">\<see> (Visual Basic)</span></span>
<span data-ttu-id="5d723-102">Gibt einen Link zu einem anderen Element an.</span><span class="sxs-lookup"><span data-stu-id="5d723-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d723-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d723-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d723-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d723-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="5d723-105">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5d723-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="5d723-106">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5d723-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="5d723-107">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="5d723-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d723-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d723-108">Remarks</span></span>  
 <span data-ttu-id="5d723-109">Verwenden Sie das `<see>`-Tag, um eine Verknüpfung innerhalb von Text anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5d723-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="5d723-110">Verwenden Sie [\<seeauch >](../../../visual-basic/language-reference/xmldoc/seealso.md) , um Text anzugeben, der möglicherweise im Abschnitt "Siehe auch" angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d723-110">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="5d723-111">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5d723-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d723-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d723-112">Example</span></span>  
 <span data-ttu-id="5d723-113">In diesem Beispiel wird das `<see>`-Tag im Abschnitt `UpdateRecord` Hinweise verwendet, um auf die `DoesRecordExist`-Methode zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="5d723-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="5d723-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d723-114">See also</span></span>

- [<span data-ttu-id="5d723-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="5d723-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
