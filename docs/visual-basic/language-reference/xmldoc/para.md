---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0846efbaf2afacd3d0783a2d2d8e4dae3fc8b715
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872709"
---
# <a name="para-visual-basic"></a><span data-ttu-id="90a2b-101">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90a2b-101">\<para> (Visual Basic)</span></span>

<span data-ttu-id="90a2b-102">Gibt an, dass der Inhalt als Absatz formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="90a2b-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90a2b-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="90a2b-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="90a2b-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="90a2b-104">Parameters</span></span>  

 `content`  
 <span data-ttu-id="90a2b-105">Der Text des Absatzes</span><span class="sxs-lookup"><span data-stu-id="90a2b-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90a2b-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90a2b-106">Remarks</span></span>  

 <span data-ttu-id="90a2b-107">Das Tag `<para>` ist für die Verwendung innerhalb eines Tags wie [\<summary>](summary.md), [\<remarks>](remarks.md) oder [\<returns>](returns.md) gedacht und ermöglicht es Ihnen, den Text zu strukturieren.</span><span class="sxs-lookup"><span data-stu-id="90a2b-107">The `<para>` tag is for use inside a tag, such as [\<summary>](summary.md), [\<remarks>](remarks.md), or [\<returns>](returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="90a2b-108">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="90a2b-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90a2b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90a2b-109">Example</span></span>  

 <span data-ttu-id="90a2b-110">In diesem Beispiel wird das- `<para>` Tag verwendet, um den Abschnitt "Hinweise" für die `UpdateRecord` Methode in zwei Absätze aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="90a2b-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="90a2b-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90a2b-111">See also</span></span>

- [<span data-ttu-id="90a2b-112">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="90a2b-112">XML Comment Tags</span></span>](index.md)
