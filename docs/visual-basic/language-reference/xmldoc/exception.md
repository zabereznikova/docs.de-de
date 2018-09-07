---
title: '&lt;Ausnahme&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 047805ad91d87550da80448fd10883ae58647bd6
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081287"
---
# <a name="ltexceptiongt-visual-basic"></a><span data-ttu-id="f2d22-102">&lt;Ausnahme&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2d22-102">&lt;exception&gt; (Visual Basic)</span></span>
<span data-ttu-id="f2d22-103">Gibt an, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="f2d22-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2d22-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2d22-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2d22-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2d22-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="f2d22-106">Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f2d22-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="f2d22-107">Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="f2d22-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="f2d22-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="f2d22-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f2d22-109">Steht für eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="f2d22-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2d22-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2d22-110">Remarks</span></span>  
 <span data-ttu-id="f2d22-111">Verwenden der `<exception>` Tag angeben, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="f2d22-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="f2d22-112">Dieses Tag wird auf eine Methodendefinition angewendet.</span><span class="sxs-lookup"><span data-stu-id="f2d22-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="f2d22-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="f2d22-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2d22-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f2d22-114">Example</span></span>  
 <span data-ttu-id="f2d22-115">Dieses Beispiel verwendet die `<exception>` Tag, um eine Ausnahme zu beschreiben, die die `IntDivide` Funktion auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="f2d22-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f2d22-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2d22-116">See Also</span></span>  
 [<span data-ttu-id="f2d22-117">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="f2d22-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
