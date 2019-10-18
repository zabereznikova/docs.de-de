---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: aa4e4c14717b69b9ca4595e20c768a2b91aac1e4
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524737"
---
# <a name="para-visual-basic"></a><span data-ttu-id="d5266-102">\<para > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5266-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="d5266-103">Gibt an, dass der Inhalt als Absatz formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="d5266-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5266-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5266-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5266-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5266-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="d5266-106">Der Text des Absatzes</span><span class="sxs-lookup"><span data-stu-id="d5266-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5266-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5266-107">Remarks</span></span>  
 <span data-ttu-id="d5266-108">Das `<para>`-Tag dient zur Verwendung innerhalb eines Tags, z. b. [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md)oder [\<returns >](../../../visual-basic/language-reference/xmldoc/returns.md), und ermöglicht das Hinzufügen von Struktur zum Text.</span><span class="sxs-lookup"><span data-stu-id="d5266-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="d5266-109">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d5266-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5266-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5266-110">Example</span></span>  
 <span data-ttu-id="d5266-111">In diesem Beispiel wird das `<para>`-Tag verwendet, um den Abschnitt "Hinweise" für die `UpdateRecord`-Methode in zwei Absätze aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="d5266-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d5266-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5266-112">See also</span></span>

- [<span data-ttu-id="d5266-113">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="d5266-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
