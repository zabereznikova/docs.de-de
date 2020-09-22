---
title: <seealso>
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: f435fa2ab86d81053cd185f5d90ec22996a1458d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869411"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="ce53a-101">\<seealso> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce53a-101">\<seealso> (Visual Basic)</span></span>

<span data-ttu-id="ce53a-102">Gibt einen Link an, der im Abschnitt "Siehe auch" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ce53a-102">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce53a-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce53a-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce53a-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce53a-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="ce53a-105">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ce53a-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="ce53a-106">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ce53a-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="ce53a-107">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ce53a-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce53a-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ce53a-108">Remarks</span></span>  

 <span data-ttu-id="ce53a-109">Verwenden Sie das- `<seealso>` Tag, um den Text anzugeben, der in einem Abschnitt Siehe auch angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce53a-109">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="ce53a-110">Mit [\<see>](see.md) kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ce53a-110">Use [\<see>](see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="ce53a-111">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ce53a-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce53a-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce53a-112">Example</span></span>  

 <span data-ttu-id="ce53a-113">In diesem Beispiel wird das- `<seealso>` Tag im Abschnitt "Hinweise" verwendet `DoesRecordExist` , um auf die-Methode zu verweisen `UpdateRecord` .</span><span class="sxs-lookup"><span data-stu-id="ce53a-113">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ce53a-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce53a-114">See also</span></span>

- [<span data-ttu-id="ce53a-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="ce53a-115">XML Comment Tags</span></span>](index.md)
