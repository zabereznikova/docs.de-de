---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 857ea1ccca4d74daf65bba03845004561afefd55
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348512"
---
# <a name="c-visual-basic"></a><span data-ttu-id="9a06b-101">\<c-> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a06b-101">\<c> (Visual Basic)</span></span>
<span data-ttu-id="9a06b-102">Gibt an, dass Text in einer Beschreibung Code ist.</span><span class="sxs-lookup"><span data-stu-id="9a06b-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a06b-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a06b-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a06b-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a06b-104">Parameters</span></span>  
  
|<span data-ttu-id="9a06b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a06b-105">Parameter</span></span>|<span data-ttu-id="9a06b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a06b-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="9a06b-107">Der Text, der als Code angegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a06b-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a06b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a06b-108">Remarks</span></span>  
 <span data-ttu-id="9a06b-109">Das `<c>`-Tag bietet Ihnen die Möglichkeit, anzugeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a06b-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="9a06b-110">Zum Angeben mehrerer Zeilen als Code wird [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a06b-110">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="9a06b-111">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9a06b-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a06b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9a06b-112">Example</span></span>  
 <span data-ttu-id="9a06b-113">In diesem Beispiel wird das `<c>`-Tag im Zusammenfassungs Abschnitt verwendet, um anzugeben, dass `Counter` Code ist.</span><span class="sxs-lookup"><span data-stu-id="9a06b-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9a06b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a06b-114">See also</span></span>

- [<span data-ttu-id="9a06b-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="9a06b-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
