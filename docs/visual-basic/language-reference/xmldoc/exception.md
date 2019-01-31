---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: b2475bd5eaeadc12e4c8c9b0fb77a2fa5cb88911
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283933"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="8da06-102">\<Ausnahme > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8da06-102">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="8da06-103">Gibt an, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="8da06-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8da06-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8da06-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8da06-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8da06-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="8da06-106">Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8da06-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="8da06-107">Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="8da06-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="8da06-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="8da06-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="8da06-109">Steht für eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="8da06-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8da06-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8da06-110">Remarks</span></span>  
 <span data-ttu-id="8da06-111">Verwenden der `<exception>` Tag angeben, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="8da06-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="8da06-112">Dieses Tag wird auf eine Methodendefinition angewendet.</span><span class="sxs-lookup"><span data-stu-id="8da06-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="8da06-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="8da06-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8da06-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8da06-114">Example</span></span>  
 <span data-ttu-id="8da06-115">Dieses Beispiel verwendet die `<exception>` Tag, um eine Ausnahme zu beschreiben, die die `IntDivide` Funktion auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="8da06-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8da06-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8da06-116">See also</span></span>
- [<span data-ttu-id="8da06-117">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="8da06-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
