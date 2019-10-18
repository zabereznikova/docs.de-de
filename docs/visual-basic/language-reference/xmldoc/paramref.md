---
title: <paramref> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 85171bd8deeb5f54c4560bb8b2339107bb8d8c68
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524708"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="1f175-102">\<paramref > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f175-102">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="1f175-103">Formatiert ein Wort als Parameter.</span><span class="sxs-lookup"><span data-stu-id="1f175-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f175-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f175-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f175-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1f175-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="1f175-106">Der Name des Parameters, auf den verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1f175-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="1f175-107">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="1f175-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f175-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1f175-108">Remarks</span></span>  
 <span data-ttu-id="1f175-109">Das `<paramref>`-Tag bietet Ihnen die Möglichkeit, anzugeben, dass ein Wort ein Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="1f175-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="1f175-110">Die XML-Datei kann verarbeitet werden, um diesen Parameter auf unterschiedliche Weise zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="1f175-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="1f175-111">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1f175-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f175-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f175-112">Example</span></span>  
 <span data-ttu-id="1f175-113">In diesem Beispiel wird das `<paramref>`-Tag verwendet, um auf den `id`-Parameter zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="1f175-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="1f175-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f175-114">See also</span></span>

- [<span data-ttu-id="1f175-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="1f175-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
