---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 4e2f441863d6a8677593a257cdb2cc841634d47c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820242"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="8292b-102">\<Ausnahme > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8292b-102">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="8292b-103">Gibt an, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="8292b-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8292b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8292b-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="8292b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8292b-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="8292b-106">Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8292b-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="8292b-107">Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="8292b-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="8292b-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="8292b-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="8292b-109">Steht für eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="8292b-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8292b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8292b-110">Remarks</span></span>  
 <span data-ttu-id="8292b-111">Verwenden der `<exception>` Tag angeben, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="8292b-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="8292b-112">Dieses Tag wird auf eine Methodendefinition angewendet.</span><span class="sxs-lookup"><span data-stu-id="8292b-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="8292b-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="8292b-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8292b-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8292b-114">Example</span></span>  
 <span data-ttu-id="8292b-115">Dieses Beispiel verwendet die `<exception>` Tag, um eine Ausnahme zu beschreiben, die die `IntDivide` Funktion auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="8292b-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8292b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8292b-116">See also</span></span>

- [<span data-ttu-id="8292b-117">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="8292b-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
