---
title: <code> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d4e887e3bbbc01e4cef5278f67b8c4afe273bf28
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524037"
---
# <a name="code-visual-basic"></a><span data-ttu-id="17b18-101">\<code > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17b18-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="17b18-102">Gibt an, dass der Text mehrere Codezeilen ist.</span><span class="sxs-lookup"><span data-stu-id="17b18-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17b18-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="17b18-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="17b18-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="17b18-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="17b18-105">Der Text, der als Code markiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="17b18-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17b18-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17b18-106">Remarks</span></span>  
 <span data-ttu-id="17b18-107">Verwenden Sie das `<code>`-Tag, um mehrere Zeilen als Code anzugeben.</span><span class="sxs-lookup"><span data-stu-id="17b18-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="17b18-108">Mit [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) wird angegeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="17b18-108">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="17b18-109">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="17b18-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17b18-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17b18-110">Example</span></span>  
 <span data-ttu-id="17b18-111">In diesem Beispiel wird das \<code >-Tags verwendet, um Beispielcode für die Verwendung des `ID`-Felds einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="17b18-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="17b18-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17b18-112">See also</span></span>

- [<span data-ttu-id="17b18-113">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="17b18-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
