---
title: <seealso>
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 5999a4ebcc90f21ee8331b96ffb2a50f7905b1b6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411511"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="93ad2-101">\<seealso> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93ad2-101">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="93ad2-102">Gibt einen Link an, der im Abschnitt "Siehe auch" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="93ad2-102">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93ad2-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="93ad2-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="93ad2-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="93ad2-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="93ad2-105">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="93ad2-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="93ad2-106">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="93ad2-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="93ad2-107">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="93ad2-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93ad2-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="93ad2-108">Remarks</span></span>  
 <span data-ttu-id="93ad2-109">Verwenden Sie das- `<seealso>` Tag, um den Text anzugeben, der in einem Abschnitt Siehe auch angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="93ad2-109">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="93ad2-110">Verwenden [\<see>](see.md) Sie, um einen Link innerhalb von Text anzugeben.</span><span class="sxs-lookup"><span data-stu-id="93ad2-110">Use [\<see>](see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="93ad2-111">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md) , um Dokumentations Kommentare in einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="93ad2-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93ad2-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93ad2-112">Example</span></span>  
 <span data-ttu-id="93ad2-113">In diesem Beispiel wird das- `<seealso>` Tag im Abschnitt "Hinweise" verwendet `DoesRecordExist` , um auf die-Methode zu verweisen `UpdateRecord` .</span><span class="sxs-lookup"><span data-stu-id="93ad2-113">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="93ad2-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93ad2-114">See also</span></span>

- [<span data-ttu-id="93ad2-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="93ad2-115">XML Comment Tags</span></span>](index.md)
