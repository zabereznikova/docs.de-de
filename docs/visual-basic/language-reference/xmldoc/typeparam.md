---
title: '&lt;Typeparam&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b654fe6fc93642693730256b523fee999aa55937
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="lttypeparamgt-visual-basic"></a><span data-ttu-id="e76af-102">&lt;Typeparam&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e76af-102">&lt;typeparam&gt; (Visual Basic)</span></span>
<span data-ttu-id="e76af-103">Definiert einen Typparametername und Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="e76af-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e76af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e76af-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e76af-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e76af-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e76af-106">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="e76af-106">The name of the type parameter.</span></span> <span data-ttu-id="e76af-107">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="e76af-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="e76af-108">Eine Beschreibung des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="e76af-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e76af-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e76af-109">Remarks</span></span>  
 <span data-ttu-id="e76af-110">Verwenden der `<typeparam>` Tag im Kommentar für einen generischen Typ oder generische Memberdeklaration, um einen der Typparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="e76af-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="e76af-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="e76af-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e76af-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e76af-112">Example</span></span>  
 <span data-ttu-id="e76af-113">Dieses Beispiel verwendet die `<typeparam>` Tag beschreiben die `id` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e76af-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e76af-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e76af-114">See Also</span></span>  
 [<span data-ttu-id="e76af-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="e76af-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
