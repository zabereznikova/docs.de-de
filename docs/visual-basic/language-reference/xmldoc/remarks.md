---
title: '&lt;"Hinweise"&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 97fca8758d9c21ac0b8f15bf9d5831750fbabe77
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863032"
---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="4179f-102">&lt;"Hinweise"&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4179f-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="4179f-103">Gibt einen Abschnitt "Hinweise" für das Element an.</span><span class="sxs-lookup"><span data-stu-id="4179f-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4179f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4179f-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4179f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4179f-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="4179f-106">Eine Beschreibung des Members</span><span class="sxs-lookup"><span data-stu-id="4179f-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4179f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4179f-107">Remarks</span></span>  
 <span data-ttu-id="4179f-108">Verwenden der `<remarks>` Tag, das Hinzufügen von Informationen zu einem Typ, die mit angegebene Informationen ergänzen [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="4179f-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="4179f-109">Diese Informationen werden im Objektkatalog angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4179f-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="4179f-110">Weitere Informationen zu den Objektkatalog, finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="4179f-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="4179f-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="4179f-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4179f-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4179f-112">Example</span></span>  
 <span data-ttu-id="4179f-113">Dieses Beispiel verwendet die `<remarks>` -Tag erläutert, was die `UpdateRecord` Methode.</span><span class="sxs-lookup"><span data-stu-id="4179f-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4179f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4179f-114">See Also</span></span>  
 [<span data-ttu-id="4179f-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="4179f-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
