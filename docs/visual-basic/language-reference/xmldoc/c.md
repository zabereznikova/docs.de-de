---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 9be9f9e96fc1b79ea97d54c54352da63b93ef264
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838039"
---
# <a name="c-visual-basic"></a><span data-ttu-id="61c08-102">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61c08-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="61c08-103">Gibt an, dass Text in einer Beschreibung Code ist.</span><span class="sxs-lookup"><span data-stu-id="61c08-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61c08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61c08-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="61c08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61c08-105">Parameters</span></span>  
  
|<span data-ttu-id="61c08-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="61c08-106">Parameter</span></span>|<span data-ttu-id="61c08-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61c08-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="61c08-108">Der Text, der als Code angegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="61c08-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61c08-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61c08-109">Remarks</span></span>  
 <span data-ttu-id="61c08-110">Die `<c>` -Tag ermöglicht es eine Möglichkeit, um anzugeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="61c08-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="61c08-111">Zum Angeben mehrerer Zeilen als Code wird [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="61c08-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="61c08-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="61c08-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61c08-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61c08-113">Example</span></span>  
 <span data-ttu-id="61c08-114">Dieses Beispiel verwendet die `<c>` -Tag im Abschnitt "Zusammenfassung" gibt an, dass `Counter` Code.</span><span class="sxs-lookup"><span data-stu-id="61c08-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="61c08-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61c08-115">See also</span></span>

- [<span data-ttu-id="61c08-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="61c08-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
