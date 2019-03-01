---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 157287ce5c85ec51f1711934cf9a5e4f568957ef
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977178"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="6e6a6-102">\<Ausnahme > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e6a6-102">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="6e6a6-103">Gibt an, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="6e6a6-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e6a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e6a6-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e6a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e6a6-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="6e6a6-106">Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6e6a6-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="6e6a6-107">Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="6e6a6-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="6e6a6-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="6e6a6-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="6e6a6-109">Steht für eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="6e6a6-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e6a6-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e6a6-110">Remarks</span></span>  
 <span data-ttu-id="6e6a6-111">Verwenden der `<exception>` Tag angeben, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="6e6a6-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="6e6a6-112">Dieses Tag wird auf eine Methodendefinition angewendet.</span><span class="sxs-lookup"><span data-stu-id="6e6a6-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="6e6a6-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="6e6a6-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e6a6-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e6a6-114">Example</span></span>  
 <span data-ttu-id="6e6a6-115">Dieses Beispiel verwendet die `<exception>` Tag, um eine Ausnahme zu beschreiben, die die `IntDivide` Funktion auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="6e6a6-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="6e6a6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e6a6-116">See also</span></span>
- [<span data-ttu-id="6e6a6-117">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="6e6a6-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
