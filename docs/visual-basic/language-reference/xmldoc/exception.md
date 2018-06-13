---
title: '&lt;Ausnahme&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: f29b8e01239f46b0d56319ba3da1a8fe179a17e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601152"
---
# <a name="ltexceptiongt-visual-basic"></a><span data-ttu-id="c6100-102">&lt;Ausnahme&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6100-102">&lt;exception&gt; (Visual Basic)</span></span>
<span data-ttu-id="c6100-103">Gibt an, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="c6100-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6100-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6100-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6100-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6100-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="c6100-106">Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c6100-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="c6100-107">Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="c6100-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="c6100-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="c6100-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="c6100-109">Eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="c6100-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6100-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6100-110">Remarks</span></span>  
 <span data-ttu-id="c6100-111">Verwenden der `<exception>` -Tag, um anzugeben, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="c6100-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="c6100-112">Dieses Tag wird auf eine Methodendefinition angewendet.</span><span class="sxs-lookup"><span data-stu-id="c6100-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="c6100-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="c6100-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6100-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c6100-114">Example</span></span>  
 <span data-ttu-id="c6100-115">Dieses Beispiel verwendet die `<exception>` -Tag, um eine Ausnahme beschrieben, die die `IntDivide` Funktion auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="c6100-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c6100-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6100-116">See Also</span></span>  
 [<span data-ttu-id="c6100-117">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="c6100-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
