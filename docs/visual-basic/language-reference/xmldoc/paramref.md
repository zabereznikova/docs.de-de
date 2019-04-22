---
title: <paramref> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 3e2bf7990343a325bbecc56f6d3754a77f1e08e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818669"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="e9766-102">\<Paramref > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9766-102">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="e9766-103">Formatiert ein Wort als Parameter an.</span><span class="sxs-lookup"><span data-stu-id="e9766-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9766-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9766-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9766-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9766-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e9766-106">Der Name des Parameters, auf den verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e9766-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="e9766-107">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="e9766-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9766-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9766-108">Remarks</span></span>  
 <span data-ttu-id="e9766-109">Die `<paramref>` -Tag ermöglicht es eine Möglichkeit, um anzugeben, dass ein Wort ein Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="e9766-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="e9766-110">Die XML-Datei kann verarbeitet werden, um diesen Parameter auf unterschiedliche Weise zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="e9766-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="e9766-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="e9766-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9766-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9766-112">Example</span></span>  
 <span data-ttu-id="e9766-113">Dieses Beispiel verwendet die `<paramref>` -Tag zum Verweisen auf die `id` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e9766-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e9766-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9766-114">See also</span></span>

- [<span data-ttu-id="e9766-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="e9766-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
