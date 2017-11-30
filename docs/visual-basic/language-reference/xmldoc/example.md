---
title: '&lt;Beispiel&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e34b75f4ce924a35dd5396b449730316025a9f35
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltexamplegt-visual-basic"></a><span data-ttu-id="e92ec-102">&lt;Beispiel&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e92ec-102">&lt;example&gt; (Visual Basic)</span></span>
<span data-ttu-id="e92ec-103">Gibt ein Beispiel für das Element an.</span><span class="sxs-lookup"><span data-stu-id="e92ec-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e92ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e92ec-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e92ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e92ec-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="e92ec-106">Eine Beschreibung des Codebeispiels.</span><span class="sxs-lookup"><span data-stu-id="e92ec-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e92ec-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e92ec-107">Remarks</span></span>  
 <span data-ttu-id="e92ec-108">Die `<example>` -Tag kann ein Beispiel zur Verwendung einer Methode oder anderen Bibliothekmembers angegeben.</span><span class="sxs-lookup"><span data-stu-id="e92ec-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="e92ec-109">Dies schließt im Allgemeinen die Verwendung des [\<code](../../../visual-basic/language-reference/xmldoc/code.md)-Tags ein.</span><span class="sxs-lookup"><span data-stu-id="e92ec-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="e92ec-110">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="e92ec-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e92ec-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e92ec-111">Example</span></span>  
 <span data-ttu-id="e92ec-112">Dieses Beispiel verwendet die `<example>` Tag enthalten ein Beispiel für die Verwendung der `ID` Feld.</span><span class="sxs-lookup"><span data-stu-id="e92ec-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e92ec-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e92ec-113">See Also</span></span>  
 [<span data-ttu-id="e92ec-114">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="e92ec-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
