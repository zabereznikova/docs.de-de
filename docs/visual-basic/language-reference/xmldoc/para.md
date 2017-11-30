---
title: '&lt;Para&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e2a034974ed94b18da374fbd372063ea4d575440
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltparagt-visual-basic"></a><span data-ttu-id="49d44-102">&lt;Para&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49d44-102">&lt;para&gt; (Visual Basic)</span></span>
<span data-ttu-id="49d44-103">Gibt an, dass der Inhalt als Absatz formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="49d44-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49d44-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49d44-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49d44-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49d44-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="49d44-106">Der Text des Absatzes</span><span class="sxs-lookup"><span data-stu-id="49d44-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49d44-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49d44-107">Remarks</span></span>  
 <span data-ttu-id="49d44-108">Die `<para>` Tag ist für die Verwendung innerhalb eines Tags, z. B. [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<"Hinweise" >](../../../visual-basic/language-reference/xmldoc/remarks.md), oder [ \<gibt >](../../../visual-basic/language-reference/xmldoc/returns.md), Zudem können Sie die Struktur der Text hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="49d44-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="49d44-109">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="49d44-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49d44-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49d44-110">Example</span></span>  
 <span data-ttu-id="49d44-111">Dieses Beispiel verwendet die `<para>` Tag aufzuteilende im Abschnitt "Hinweise" der `UpdateRecord` Methode in beiden Absätze tauschen.</span><span class="sxs-lookup"><span data-stu-id="49d44-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="49d44-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49d44-112">See Also</span></span>  
 [<span data-ttu-id="49d44-113">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="49d44-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
