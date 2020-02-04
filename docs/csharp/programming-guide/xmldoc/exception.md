---
title: <exception> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 14318ac0b0cdf781d0488eecaf934879017d91f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789800"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="b3406-102">\<exception> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b3406-102">\<exception> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="b3406-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3406-103">Syntax</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a><span data-ttu-id="b3406-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="b3406-104">Parameters</span></span>

- <span data-ttu-id="b3406-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="b3406-105">cref = " `member`"</span></span>

  <span data-ttu-id="b3406-106">Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b3406-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="b3406-107">Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="b3406-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="b3406-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="b3406-108">`member` must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="b3406-109">Weitere Informationen zum Formatieren von `member` für das Verweisen auf einen generischen Typ finden Sie unter [Verarbeiten der XML-Datei](processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="b3406-109">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>

- `description`

  <span data-ttu-id="b3406-110">Eine Beschreibung der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="b3406-110">A description of the exception.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3406-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b3406-111">Remarks</span></span>

<span data-ttu-id="b3406-112">Mit dem Tag \<exception> können Sie angeben, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="b3406-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="b3406-113">Dieses Tag kann für Definitionen für Methoden, Eigenschaften, Ereignisse und Indexer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b3406-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>

<span data-ttu-id="b3406-114">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b3406-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="b3406-115">Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Ausnahmen und Ausnahmebehandlung](../exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="b3406-115">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="b3406-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3406-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a><span data-ttu-id="b3406-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3406-117">See also</span></span>

- [<span data-ttu-id="b3406-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b3406-118">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="b3406-119">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="b3406-119">Recommended tags for documentation comments</span></span>](recommended-tags-for-documentation-comments.md)
