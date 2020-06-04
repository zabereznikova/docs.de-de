---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0e2051d1b00b881c06082b3af483890d8595899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400072"
---
# <a name="para-visual-basic"></a><span data-ttu-id="06c71-101">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06c71-101">\<para> (Visual Basic)</span></span>
<span data-ttu-id="06c71-102">Gibt an, dass der Inhalt als Absatz formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="06c71-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06c71-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="06c71-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="06c71-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="06c71-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="06c71-105">Der Text des Absatzes</span><span class="sxs-lookup"><span data-stu-id="06c71-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06c71-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06c71-106">Remarks</span></span>  
 <span data-ttu-id="06c71-107">Das `<para>` -Tag dient zur Verwendung innerhalb eines Tags, z [\<summary>](summary.md) [\<remarks>](remarks.md) . b., oder [\<returns>](returns.md) , und ermöglicht das Hinzufügen von Struktur zum Text.</span><span class="sxs-lookup"><span data-stu-id="06c71-107">The `<para>` tag is for use inside a tag, such as [\<summary>](summary.md), [\<remarks>](remarks.md), or [\<returns>](returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="06c71-108">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="06c71-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06c71-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06c71-109">Example</span></span>  
 <span data-ttu-id="06c71-110">In diesem Beispiel wird das- `<para>` Tag verwendet, um den Abschnitt "Hinweise" für die `UpdateRecord` Methode in zwei Absätze aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="06c71-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="06c71-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06c71-111">See also</span></span>

- [<span data-ttu-id="06c71-112">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="06c71-112">XML Comment Tags</span></span>](index.md)
