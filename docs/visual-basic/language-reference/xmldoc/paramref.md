---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: d7aacc5faea22f9c5a4b865a32c832154fe624c5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872619"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="d36aa-101">\<paramref> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d36aa-101">\<paramref> (Visual Basic)</span></span>

<span data-ttu-id="d36aa-102">Formatiert ein Wort als Parameter.</span><span class="sxs-lookup"><span data-stu-id="d36aa-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d36aa-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="d36aa-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d36aa-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="d36aa-104">Parameters</span></span>  

 `name`  
 <span data-ttu-id="d36aa-105">Der Name des Parameters, auf den verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d36aa-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="d36aa-106">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="d36aa-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d36aa-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d36aa-107">Remarks</span></span>  

 <span data-ttu-id="d36aa-108">Das- `<paramref>` Tag bietet Ihnen die Möglichkeit, anzugeben, dass ein Wort ein Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="d36aa-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="d36aa-109">Die XML-Datei kann verarbeitet werden, um diesen Parameter auf unterschiedliche Weise zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="d36aa-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="d36aa-110">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d36aa-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d36aa-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d36aa-111">Example</span></span>  

 <span data-ttu-id="d36aa-112">In diesem Beispiel wird das- `<paramref>` Tag zum Verweisen auf den- `id` Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="d36aa-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d36aa-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d36aa-113">See also</span></span>

- [<span data-ttu-id="d36aa-114">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="d36aa-114">XML Comment Tags</span></span>](index.md)
