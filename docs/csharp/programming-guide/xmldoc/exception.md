---
title: '&lt;exception&gt; (C#-Programmierhandbuch)'
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: c865fe97db16c95396e03747958d3590e80de614
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259687"
---
# <a name="ltexceptiongt-c-programming-guide"></a><span data-ttu-id="85f1b-102">&lt;exception&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="85f1b-102">&lt;exception&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="85f1b-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="85f1b-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85f1b-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="85f1b-104">Parameters</span></span>  
 <span data-ttu-id="85f1b-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="85f1b-105">cref = " `member`"</span></span>  
 <span data-ttu-id="85f1b-106">Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="85f1b-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="85f1b-107">Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="85f1b-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="85f1b-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="85f1b-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="85f1b-109">Weitere Informationen zum Erstellen von cref-Verweisen auf einen generischen Typ finden Sie unter [\<see](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="85f1b-109">For more information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="85f1b-110">Eine Beschreibung der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="85f1b-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85f1b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85f1b-111">Remarks</span></span>  
 <span data-ttu-id="85f1b-112">Mit dem Tag \<exception> können Sie angeben, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="85f1b-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="85f1b-113">Dieses Tag kann für Definitionen für Methoden, Eigenschaften, Ereignisse und Indexer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="85f1b-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="85f1b-114">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="85f1b-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="85f1b-115">Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="85f1b-115">For more information about exception handling, see [Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85f1b-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85f1b-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="85f1b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85f1b-117">See Also</span></span>

- [<span data-ttu-id="85f1b-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="85f1b-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="85f1b-119">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="85f1b-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
