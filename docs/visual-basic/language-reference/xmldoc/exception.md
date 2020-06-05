---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 3a2452ec60a2182adfee365777d9824001ff006a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400123"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="97c42-101">\<exception> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97c42-101">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="97c42-102">Gibt an, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="97c42-102">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97c42-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="97c42-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="97c42-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="97c42-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="97c42-105">Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="97c42-105">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="97c42-106">Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="97c42-106">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="97c42-107">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="97c42-107">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="97c42-108">Eine Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97c42-108">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97c42-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="97c42-109">Remarks</span></span>  
 <span data-ttu-id="97c42-110">Verwenden Sie das- `<exception>` Tag, um anzugeben, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="97c42-110">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="97c42-111">Dieses Tag wird auf eine Methodendefinition angewendet.</span><span class="sxs-lookup"><span data-stu-id="97c42-111">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="97c42-112">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md) , um Dokumentations Kommentare in einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="97c42-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97c42-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97c42-113">Example</span></span>  
 <span data-ttu-id="97c42-114">In diesem Beispiel wird das- `<exception>` Tag verwendet, um eine Ausnahme zu beschreiben, die die `IntDivide` Funktion auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="97c42-114">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="97c42-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97c42-115">See also</span></span>

- [<span data-ttu-id="97c42-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="97c42-116">XML Comment Tags</span></span>](index.md)
