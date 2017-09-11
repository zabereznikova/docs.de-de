---
title: '&lt;Hinweise&gt; (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: c1b2c48dc3247935f703ff4107f29829c494a305
ms.contentlocale: de-de
ms.lasthandoff: 06/01/2017

---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="be848-102">&lt;Hinweise&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be848-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="be848-103">Gibt einen Hinweisabschnitt für den Member.</span><span class="sxs-lookup"><span data-stu-id="be848-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be848-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be848-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be848-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be848-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="be848-106">Eine Beschreibung des Elements.</span><span class="sxs-lookup"><span data-stu-id="be848-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be848-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be848-107">Remarks</span></span>  
 <span data-ttu-id="be848-108">Verwenden der `<remarks>` Tag Hinzufügen von Informationen zu einem Typ, der mit angegebenen mittels [ \<Zusammenfassung >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="be848-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="be848-109">Diese Informationen werden im Objektkatalog angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be848-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="be848-110">Informationen über den Objektkatalog finden Sie unter [Anzeigen der Struktur des Codes](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="be848-110">For information about the Object Browser, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="be848-111">Kompilieren Sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) Dokumentationskommentare zu einer Datei.</span><span class="sxs-lookup"><span data-stu-id="be848-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be848-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be848-112">Example</span></span>  
 <span data-ttu-id="be848-113">Dieses Beispiel verwendet die `<remarks>` -Tag erläutert, was die `UpdateRecord` Methode.</span><span class="sxs-lookup"><span data-stu-id="be848-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 <span data-ttu-id="be848-114">[!code-vb[VbVbcnXmlDocComments&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="be848-114">[!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be848-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be848-115">See Also</span></span>  
 [<span data-ttu-id="be848-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="be848-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
