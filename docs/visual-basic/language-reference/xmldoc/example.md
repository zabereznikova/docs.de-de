---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 510b00d2220b9c65b0e2b8fa3ead70925a9f54ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821919"
---
# <a name="example-visual-basic"></a><span data-ttu-id="e9c08-102">\<Beispiel > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9c08-102">\<example> (Visual Basic)</span></span>
<span data-ttu-id="e9c08-103">Gibt ein Beispiel für das Element an.</span><span class="sxs-lookup"><span data-stu-id="e9c08-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9c08-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9c08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9c08-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="e9c08-106">Eine Beschreibung des Codebeispiels.</span><span class="sxs-lookup"><span data-stu-id="e9c08-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9c08-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9c08-107">Remarks</span></span>  
 <span data-ttu-id="e9c08-108">Die `<example>` -Tag können Sie ein Beispiel zur Verwendung einer Methode oder anderen Bibliothekmembers angegeben.</span><span class="sxs-lookup"><span data-stu-id="e9c08-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="e9c08-109">Dies schließt im Allgemeinen die Verwendung des [\<code](../../../visual-basic/language-reference/xmldoc/code.md)-Tags ein.</span><span class="sxs-lookup"><span data-stu-id="e9c08-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="e9c08-110">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="e9c08-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9c08-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9c08-111">Example</span></span>  
 <span data-ttu-id="e9c08-112">Dieses Beispiel verwendet die `<example>` Tag enthalten ein Beispiel für die Verwendung der `ID` Feld.</span><span class="sxs-lookup"><span data-stu-id="e9c08-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e9c08-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9c08-113">See also</span></span>

- [<span data-ttu-id="e9c08-114">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="e9c08-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
