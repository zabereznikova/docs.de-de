---
title: <exception> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <exception>. Mit diesem Tag können Sie angeben, welche Ausnahmen ausgelöst werden können. Es kann auf Methoden, Eigenschaften, Ereignisse und Indexer angewendet werden.
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 22a28f3fe6de5a0db9aea0f1fd7963d4e6fcee05
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381735"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="2b354-104">\<exception> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2b354-104">\<exception> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="2b354-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b354-105">Syntax</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a><span data-ttu-id="2b354-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b354-106">Parameters</span></span>

- <span data-ttu-id="2b354-107">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="2b354-107">cref = " `member`"</span></span>

  <span data-ttu-id="2b354-108">Ein Verweis auf eine Ausnahme, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2b354-108">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="2b354-109">Der Compiler prüft, ob die angegebene Ausnahme vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="2b354-109">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="2b354-110">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="2b354-110">`member` must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="2b354-111">Weitere Informationen zum Formatieren von `member` für das Verweisen auf einen generischen Typ finden Sie unter [Verarbeiten der XML-Datei](processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="2b354-111">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>

- `description`

  <span data-ttu-id="2b354-112">Eine Beschreibung der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="2b354-112">A description of the exception.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b354-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b354-113">Remarks</span></span>

<span data-ttu-id="2b354-114">Mit dem Tag `<exception>` können Sie angeben, welche Ausnahmen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="2b354-114">The `<exception>` tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="2b354-115">Dieses Tag kann für Definitionen für Methoden, Eigenschaften, Ereignisse und Indexer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b354-115">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>

<span data-ttu-id="2b354-116">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2b354-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="2b354-117">Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Ausnahmen und Ausnahmebehandlung](../exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="2b354-117">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="2b354-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b354-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a><span data-ttu-id="2b354-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b354-119">See also</span></span>

- [<span data-ttu-id="2b354-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2b354-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="2b354-121">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="2b354-121">Recommended tags for documentation comments</span></span>](recommended-tags-for-documentation-comments.md)
