---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 06c6899895f278fdf652725a05ecc7229805f4d4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43854729"
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="81a49-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81a49-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="81a49-103">Gibt an, dass Text in einer Beschreibung Code ist.</span><span class="sxs-lookup"><span data-stu-id="81a49-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81a49-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81a49-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81a49-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="81a49-105">Parameters</span></span>  
  
|<span data-ttu-id="81a49-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="81a49-106">Parameter</span></span>|<span data-ttu-id="81a49-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81a49-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="81a49-108">Der Text, der als Code angegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="81a49-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81a49-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81a49-109">Remarks</span></span>  
 <span data-ttu-id="81a49-110">Die `<c>` -Tag ermöglicht es eine Möglichkeit, um anzugeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="81a49-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="81a49-111">Zum Angeben mehrerer Zeilen als Code wird [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="81a49-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="81a49-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="81a49-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81a49-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81a49-113">Example</span></span>  
 <span data-ttu-id="81a49-114">Dieses Beispiel verwendet die `<c>` -Tag im Abschnitt "Zusammenfassung" gibt an, dass `Counter` Code.</span><span class="sxs-lookup"><span data-stu-id="81a49-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="81a49-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81a49-115">See Also</span></span>  
 [<span data-ttu-id="81a49-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="81a49-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
