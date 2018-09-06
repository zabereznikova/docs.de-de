---
title: '&lt;Typeparam&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: d362f181921a39d274eaee78e85976522ce4fc15
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863188"
---
# <a name="lttypeparamgt-visual-basic"></a><span data-ttu-id="c59b8-102">&lt;Typeparam&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c59b8-102">&lt;typeparam&gt; (Visual Basic)</span></span>
<span data-ttu-id="c59b8-103">Definiert einen Typparametername und Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="c59b8-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c59b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c59b8-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c59b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c59b8-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="c59b8-106">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="c59b8-106">The name of the type parameter.</span></span> <span data-ttu-id="c59b8-107">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="c59b8-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="c59b8-108">Eine Beschreibung des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="c59b8-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c59b8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c59b8-109">Remarks</span></span>  
 <span data-ttu-id="c59b8-110">Verwenden der `<typeparam>` Tag im Kommentar für einen generischen Typ oder generische Memberdeklaration, um einen der Typparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="c59b8-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="c59b8-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="c59b8-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c59b8-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c59b8-112">Example</span></span>  
 <span data-ttu-id="c59b8-113">Dieses Beispiel verwendet die `<typeparam>` Tag zum Beschreiben der `id` Parameter.</span><span class="sxs-lookup"><span data-stu-id="c59b8-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c59b8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c59b8-114">See Also</span></span>  
 [<span data-ttu-id="c59b8-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="c59b8-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
