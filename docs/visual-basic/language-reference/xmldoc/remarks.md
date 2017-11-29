---
title: '&lt;"Hinweise"&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f70c2d7df190d2ff8187882a9176dbe98984296
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="5504f-102">&lt;"Hinweise"&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5504f-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="5504f-103">Gibt einen Abschnitt "Hinweise" für das Element an.</span><span class="sxs-lookup"><span data-stu-id="5504f-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5504f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5504f-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5504f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5504f-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="5504f-106">Eine Beschreibung des Members</span><span class="sxs-lookup"><span data-stu-id="5504f-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5504f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5504f-107">Remarks</span></span>  
 <span data-ttu-id="5504f-108">Verwenden der `<remarks>` -Tag, um Informationen über einen Typ, ergänzen die Informationen, die mit angegebenen hinzufügen [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="5504f-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="5504f-109">Diese Informationen werden im Objektkatalog angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5504f-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="5504f-110">Informationen über den Objektkatalog finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="5504f-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="5504f-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="5504f-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5504f-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5504f-112">Example</span></span>  
 <span data-ttu-id="5504f-113">Dieses Beispiel verwendet die `<remarks>` -Tag erläutert, was die `UpdateRecord` Methode hat.</span><span class="sxs-lookup"><span data-stu-id="5504f-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5504f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5504f-114">See Also</span></span>  
 [<span data-ttu-id="5504f-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="5504f-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
