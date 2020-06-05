---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 3ca08016d3cef0c44e4f3c0bd0d017628eda606d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400046"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="6fc0c-101">\<paramref> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fc0c-101">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="6fc0c-102">Formatiert ein Wort als Parameter.</span><span class="sxs-lookup"><span data-stu-id="6fc0c-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fc0c-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fc0c-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fc0c-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="6fc0c-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6fc0c-105">Der Name des Parameters, auf den verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6fc0c-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="6fc0c-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="6fc0c-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fc0c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6fc0c-107">Remarks</span></span>  
 <span data-ttu-id="6fc0c-108">Das- `<paramref>` Tag bietet Ihnen die Möglichkeit, anzugeben, dass ein Wort ein Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="6fc0c-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="6fc0c-109">Die XML-Datei kann verarbeitet werden, um diesen Parameter auf unterschiedliche Weise zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="6fc0c-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="6fc0c-110">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6fc0c-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fc0c-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fc0c-111">Example</span></span>  
 <span data-ttu-id="6fc0c-112">In diesem Beispiel wird das- `<paramref>` Tag zum Verweisen auf den- `id` Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fc0c-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="6fc0c-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6fc0c-113">See also</span></span>

- [<span data-ttu-id="6fc0c-114">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="6fc0c-114">XML Comment Tags</span></span>](index.md)
