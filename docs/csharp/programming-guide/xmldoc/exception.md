---
title: <exception> – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: fe304b9c6631591cf7a3d62fcecd2ed3ca05db9c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257290"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="4870f-102">\<exception> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4870f-102">\<exception> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4870f-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="4870f-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4870f-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="4870f-104">Parameters</span></span>  
 <span data-ttu-id="4870f-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="4870f-105">cref = " `member`"</span></span>  
 <span data-ttu-id="4870f-106">Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4870f-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="4870f-107">Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="4870f-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="4870f-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="4870f-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="4870f-109">Weitere Informationen zum Erstellen von cref-Verweisen auf einen generischen Typ finden Sie unter [\<see](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="4870f-109">For more information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="4870f-110">Eine Beschreibung der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="4870f-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4870f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4870f-111">Remarks</span></span>  
 <span data-ttu-id="4870f-112">Mit dem Tag \<exception> können Sie angeben, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="4870f-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="4870f-113">Dieses Tag kann für Definitionen für Methoden, Eigenschaften, Ereignisse und Indexer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="4870f-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="4870f-114">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="4870f-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="4870f-115">Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="4870f-115">For more information about exception handling, see [Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4870f-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4870f-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4870f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4870f-117">See also</span></span>

- [<span data-ttu-id="4870f-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4870f-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4870f-119">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="4870f-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
