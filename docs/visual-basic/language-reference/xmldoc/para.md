---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 8f28ecc33eea99150509bb4bade047489b4b826b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352307"
---
# <a name="para-visual-basic"></a><span data-ttu-id="e7546-101">\<para > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7546-101">\<para> (Visual Basic)</span></span>
<span data-ttu-id="e7546-102">Gibt an, dass der Inhalt als Absatz formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="e7546-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7546-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7546-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7546-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7546-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="e7546-105">Der Text des Absatzes</span><span class="sxs-lookup"><span data-stu-id="e7546-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7546-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7546-106">Remarks</span></span>  
 <span data-ttu-id="e7546-107">Das `<para>`-Tag dient zur Verwendung innerhalb eines Tags, z. b. [\<Zusammenfassungs >](../../../visual-basic/language-reference/xmldoc/summary.md), [\<Anmerkungen >](../../../visual-basic/language-reference/xmldoc/remarks.md), oder [\<gibt > zurück](../../../visual-basic/language-reference/xmldoc/returns.md), und Sie können dem Text Struktur hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e7546-107">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="e7546-108">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e7546-108">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7546-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7546-109">Example</span></span>  
 <span data-ttu-id="e7546-110">In diesem Beispiel wird das `<para>`-Tag verwendet, um den Abschnitt "Hinweise" für die `UpdateRecord`-Methode in zwei Absätze aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="e7546-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e7546-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7546-111">See also</span></span>

- [<span data-ttu-id="e7546-112">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="e7546-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
