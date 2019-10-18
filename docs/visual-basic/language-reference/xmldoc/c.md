---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 4ea19ed5330dcbb8fcd84708d1546a81d909b04e
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523938"
---
# <a name="c-visual-basic"></a><span data-ttu-id="d6088-102">\<c > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6088-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="d6088-103">Gibt an, dass Text in einer Beschreibung Code ist.</span><span class="sxs-lookup"><span data-stu-id="d6088-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6088-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6088-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6088-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6088-105">Parameters</span></span>  
  
|<span data-ttu-id="d6088-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6088-106">Parameter</span></span>|<span data-ttu-id="d6088-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6088-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="d6088-108">Der Text, der als Code angegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6088-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6088-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6088-109">Remarks</span></span>  
 <span data-ttu-id="d6088-110">Das `<c>`-Tag bietet Ihnen die Möglichkeit, anzugeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6088-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="d6088-111">Zum Angeben mehrerer Zeilen als Code wird [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6088-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="d6088-112">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d6088-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6088-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6088-113">Example</span></span>  
 <span data-ttu-id="d6088-114">In diesem Beispiel wird das `<c>`-Tag im Zusammenfassungs Abschnitt verwendet, um anzugeben, dass `Counter` Code ist.</span><span class="sxs-lookup"><span data-stu-id="d6088-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d6088-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6088-115">See also</span></span>

- [<span data-ttu-id="d6088-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="d6088-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
