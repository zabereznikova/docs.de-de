---
title: '&lt;Gibt&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6130a6fabe450900fe19ef4d361654508f907ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltreturnsgt-visual-basic"></a><span data-ttu-id="640ef-102">&lt;Gibt&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="640ef-102">&lt;returns&gt; (Visual Basic)</span></span>
<span data-ttu-id="640ef-103">Gibt den Rückgabewert der Eigenschaft oder Funktion.</span><span class="sxs-lookup"><span data-stu-id="640ef-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="640ef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="640ef-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="640ef-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="640ef-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="640ef-106">Eine Beschreibung des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="640ef-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="640ef-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="640ef-107">Remarks</span></span>  
 <span data-ttu-id="640ef-108">Verwenden der `<returns>` Tag im Kommentar für eine Methodendeklaration, um den Rückgabewert beschreiben.</span><span class="sxs-lookup"><span data-stu-id="640ef-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="640ef-109">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="640ef-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="640ef-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="640ef-110">Example</span></span>  
 <span data-ttu-id="640ef-111">Dieses Beispiel verwendet die `<returns>` -Tag erläutert, was die `DoesRecordExist` -Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="640ef-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="640ef-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="640ef-112">See Also</span></span>  
 [<span data-ttu-id="640ef-113">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="640ef-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
