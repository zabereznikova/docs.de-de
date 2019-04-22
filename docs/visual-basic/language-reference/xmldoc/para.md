---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 16d10b2f955a4d9a02075ee4cc40dfa2b18c3541
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814509"
---
# <a name="para-visual-basic"></a><span data-ttu-id="c9dd9-102">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9dd9-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="c9dd9-103">Gibt an, dass der Inhalt als ein Absatz formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="c9dd9-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9dd9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9dd9-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9dd9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9dd9-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="c9dd9-106">Der Text des Absatzes</span><span class="sxs-lookup"><span data-stu-id="c9dd9-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9dd9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9dd9-107">Remarks</span></span>  
 <span data-ttu-id="c9dd9-108">Die `<para>` Tag ist für die Verwendung innerhalb eines Tags wie z. B. [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<"Hinweise" >](../../../visual-basic/language-reference/xmldoc/remarks.md), oder [ \<gibt >](../../../visual-basic/language-reference/xmldoc/returns.md), und können Sie die Struktur auf den Text hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c9dd9-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="c9dd9-109">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="c9dd9-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9dd9-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c9dd9-110">Example</span></span>  
 <span data-ttu-id="c9dd9-111">Dieses Beispiel verwendet die `<para>` Tag, teilen den Abschnitt "Hinweise" der `UpdateRecord` Methode in beiden Absätze tauschen.</span><span class="sxs-lookup"><span data-stu-id="c9dd9-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="c9dd9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9dd9-112">See also</span></span>

- [<span data-ttu-id="c9dd9-113">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="c9dd9-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
