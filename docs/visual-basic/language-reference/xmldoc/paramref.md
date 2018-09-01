---
title: '&lt;Paramref&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 153f5ddeeb7d09159049af4d466b0695f5cb6f23
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393444"
---
# <a name="ltparamrefgt-visual-basic"></a><span data-ttu-id="87028-102">&lt;Paramref&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87028-102">&lt;paramref&gt; (Visual Basic)</span></span>
<span data-ttu-id="87028-103">Formatiert ein Wort als Parameter an.</span><span class="sxs-lookup"><span data-stu-id="87028-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87028-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87028-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87028-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="87028-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="87028-106">Der Name des Parameters, auf den verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="87028-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="87028-107">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="87028-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87028-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87028-108">Remarks</span></span>  
 <span data-ttu-id="87028-109">Die `<paramref>` -Tag ermöglicht es eine Möglichkeit, um anzugeben, dass ein Wort ein Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="87028-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="87028-110">Die XML-Datei kann verarbeitet werden, um diesen Parameter auf unterschiedliche Weise zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="87028-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="87028-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="87028-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87028-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87028-112">Example</span></span>  
 <span data-ttu-id="87028-113">Dieses Beispiel verwendet die `<paramref>` -Tag zum Verweisen auf die `id` Parameter.</span><span class="sxs-lookup"><span data-stu-id="87028-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/paramref_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="87028-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87028-114">See Also</span></span>  
 [<span data-ttu-id="87028-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="87028-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
