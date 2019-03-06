---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: cbb8e3b1e67150473159835ba2cd58d9ddf0c1c1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479007"
---
# <a name="para-visual-basic"></a><span data-ttu-id="fdacf-102">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdacf-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="fdacf-103">Gibt an, dass der Inhalt als ein Absatz formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="fdacf-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdacf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdacf-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdacf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fdacf-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="fdacf-106">Der Text des Absatzes</span><span class="sxs-lookup"><span data-stu-id="fdacf-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdacf-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fdacf-107">Remarks</span></span>  
 <span data-ttu-id="fdacf-108">Die `<para>` Tag ist für die Verwendung innerhalb eines Tags wie z. B. [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<"Hinweise" >](../../../visual-basic/language-reference/xmldoc/remarks.md), oder [ \<gibt >](../../../visual-basic/language-reference/xmldoc/returns.md), und können Sie die Struktur auf den Text hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fdacf-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="fdacf-109">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="fdacf-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdacf-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fdacf-110">Example</span></span>  
 <span data-ttu-id="fdacf-111">Dieses Beispiel verwendet die `<para>` Tag, teilen den Abschnitt "Hinweise" der `UpdateRecord` Methode in beiden Absätze tauschen.</span><span class="sxs-lookup"><span data-stu-id="fdacf-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="fdacf-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdacf-112">See also</span></span>
- [<span data-ttu-id="fdacf-113">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="fdacf-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
