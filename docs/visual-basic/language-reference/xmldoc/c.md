---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 969df339eb766d2edb444ab5626af4e69accddba
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871697"
---
# <a name="c-visual-basic"></a><span data-ttu-id="a6137-101">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6137-101">\<c> (Visual Basic)</span></span>

<span data-ttu-id="a6137-102">Gibt an, dass Text in einer Beschreibung Code ist.</span><span class="sxs-lookup"><span data-stu-id="a6137-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6137-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6137-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6137-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6137-104">Parameters</span></span>  
  
|<span data-ttu-id="a6137-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6137-105">Parameter</span></span>|<span data-ttu-id="a6137-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a6137-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="a6137-107">Der Text, der als Code angegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6137-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6137-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6137-108">Remarks</span></span>  

 <span data-ttu-id="a6137-109">Mit dem `<c>`-Tag kann angegeben werden, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6137-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="a6137-110">Zum Angeben mehrerer Zeilen als Code wird [\<code>](code.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6137-110">Use [\<code>](code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="a6137-111">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a6137-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6137-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6137-112">Example</span></span>  

 <span data-ttu-id="a6137-113">In diesem Beispiel wird das- `<c>` Tag im Zusammenfassungs Abschnitt verwendet, um anzugeben, dass der `Counter` Code ist.</span><span class="sxs-lookup"><span data-stu-id="a6137-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a6137-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6137-114">See also</span></span>

- [<span data-ttu-id="a6137-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="a6137-115">XML Comment Tags</span></span>](index.md)
