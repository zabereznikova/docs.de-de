---
title: '&lt;Code&gt; (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7c1d8ab3db0c36c6a2935b9ffbef15e87df5ebc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltcodegt-visual-basic"></a><span data-ttu-id="c37bf-102">&lt;Code&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c37bf-102">&lt;code&gt; (Visual Basic)</span></span>
<span data-ttu-id="c37bf-103">Gibt an, dass der Text mehrere Codezeilen.</span><span class="sxs-lookup"><span data-stu-id="c37bf-103">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c37bf-104">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c37bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c37bf-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="c37bf-106">Der Text, der als Code zu markieren.</span><span class="sxs-lookup"><span data-stu-id="c37bf-106">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c37bf-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c37bf-107">Remarks</span></span>  
 <span data-ttu-id="c37bf-108">Verwenden der `<code>` -Tag, um mehrere Zeilen als Code anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c37bf-108">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="c37bf-109">Mit [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) wird angegeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c37bf-109">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="c37bf-110">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="c37bf-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c37bf-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c37bf-111">Example</span></span>  
 <span data-ttu-id="c37bf-112">Dieses Beispiel verwendet die \<Code >-Tag, um den Beispielcode für die Verwendung der `ID` Feld.</span><span class="sxs-lookup"><span data-stu-id="c37bf-112">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c37bf-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c37bf-113">See Also</span></span>  
 [<span data-ttu-id="c37bf-114">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="c37bf-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
