---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d058663213cf02f2142bff740aeec1b60791362c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873035"
---
# <a name="code-visual-basic"></a><span data-ttu-id="1e628-101">\<code> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e628-101">\<code> (Visual Basic)</span></span>

<span data-ttu-id="1e628-102">Gibt an, dass der Text mehrere Codezeilen ist.</span><span class="sxs-lookup"><span data-stu-id="1e628-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e628-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e628-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e628-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e628-104">Parameters</span></span>  

 `content`  
 <span data-ttu-id="1e628-105">Der Text, der als Code markiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1e628-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e628-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e628-106">Remarks</span></span>  

 <span data-ttu-id="1e628-107">Verwenden Sie das- `<code>` Tag, um mehrere Zeilen als Code anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1e628-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="1e628-108">Verwenden [\<c>](c.md) Sie, um anzugeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1e628-108">Use [\<c>](c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="1e628-109">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1e628-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e628-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e628-110">Example</span></span>  

 <span data-ttu-id="1e628-111">In diesem Beispiel wird das- \<code> Tag verwendet, um Beispielcode für die Verwendung des- `ID` Felds einzufügen.</span><span class="sxs-lookup"><span data-stu-id="1e628-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1e628-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e628-112">See also</span></span>

- [<span data-ttu-id="1e628-113">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="1e628-113">XML Comment Tags</span></span>](index.md)
