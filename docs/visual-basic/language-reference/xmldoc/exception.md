---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: e1e7f2d0fb06599f83ba224ed52a10429d9b11fe
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346961"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="e7575-101">\<Ausnahme > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7575-101">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="e7575-102">Gibt an, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="e7575-102">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7575-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7575-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7575-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7575-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="e7575-105">Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e7575-105">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="e7575-106">Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="e7575-106">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="e7575-107">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="e7575-107">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="e7575-108">Steht für eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="e7575-108">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7575-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7575-109">Remarks</span></span>  
 <span data-ttu-id="e7575-110">Verwenden Sie das `<exception>`-Tag, um anzugeben, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="e7575-110">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="e7575-111">Dieses Tag wird auf eine Methodendefinition angewendet.</span><span class="sxs-lookup"><span data-stu-id="e7575-111">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="e7575-112">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e7575-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7575-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7575-113">Example</span></span>  
 <span data-ttu-id="e7575-114">In diesem Beispiel wird das `<exception>`-Tag verwendet, um eine Ausnahme zu beschreiben, die die `IntDivide`-Funktion auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="e7575-114">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e7575-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7575-115">See also</span></span>

- [<span data-ttu-id="e7575-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="e7575-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
