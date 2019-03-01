---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 90f358aad8e3219b2e3cb3e9b996a24b3138828b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970830"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="0973b-102">\<remarks> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0973b-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="0973b-103">Gibt einen Abschnitt "Hinweise" für das Element an.</span><span class="sxs-lookup"><span data-stu-id="0973b-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0973b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0973b-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0973b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0973b-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="0973b-106">Eine Beschreibung des Members</span><span class="sxs-lookup"><span data-stu-id="0973b-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0973b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0973b-107">Remarks</span></span>  
 <span data-ttu-id="0973b-108">Verwenden der `<remarks>` Tag, das Hinzufügen von Informationen zu einem Typ, die mit angegebene Informationen ergänzen [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="0973b-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="0973b-109">Diese Informationen werden im Objektkatalog angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0973b-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="0973b-110">Weitere Informationen zu den Objektkatalog, finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="0973b-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="0973b-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="0973b-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0973b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0973b-112">Example</span></span>  
 <span data-ttu-id="0973b-113">Dieses Beispiel verwendet die `<remarks>` -Tag erläutert, was die `UpdateRecord` Methode.</span><span class="sxs-lookup"><span data-stu-id="0973b-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0973b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0973b-114">See also</span></span>
- [<span data-ttu-id="0973b-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="0973b-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
