---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: a1dea0bcc40de8dea986e93a25617f607383ec21
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969218"
---
# <a name="example-visual-basic"></a><span data-ttu-id="d93b9-102">\<Beispiel > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d93b9-102">\<example> (Visual Basic)</span></span>
<span data-ttu-id="d93b9-103">Gibt ein Beispiel für das Element an.</span><span class="sxs-lookup"><span data-stu-id="d93b9-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d93b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d93b9-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d93b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d93b9-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="d93b9-106">Eine Beschreibung des Codebeispiels.</span><span class="sxs-lookup"><span data-stu-id="d93b9-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d93b9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d93b9-107">Remarks</span></span>  
 <span data-ttu-id="d93b9-108">Die `<example>` -Tag können Sie ein Beispiel zur Verwendung einer Methode oder anderen Bibliothekmembers angegeben.</span><span class="sxs-lookup"><span data-stu-id="d93b9-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="d93b9-109">Dies schließt im Allgemeinen die Verwendung des [\<code](../../../visual-basic/language-reference/xmldoc/code.md)-Tags ein.</span><span class="sxs-lookup"><span data-stu-id="d93b9-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="d93b9-110">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="d93b9-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d93b9-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d93b9-111">Example</span></span>  
 <span data-ttu-id="d93b9-112">Dieses Beispiel verwendet die `<example>` Tag enthalten ein Beispiel für die Verwendung der `ID` Feld.</span><span class="sxs-lookup"><span data-stu-id="d93b9-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d93b9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d93b9-113">See also</span></span>
- [<span data-ttu-id="d93b9-114">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="d93b9-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
