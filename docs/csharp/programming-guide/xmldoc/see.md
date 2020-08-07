---
title: <see> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <see>. Mit diesem Tag können Sie einen Link im Text angeben, z. B. durch Verwendung eines cref-Attributs.
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 1cc4982d1ebe9d6896404218a6d200b10cc6503f
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381930"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="e7bdf-104">\<see> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="e7bdf-104">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="e7bdf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7bdf-105">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="e7bdf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7bdf-106">Parameters</span></span>

- <span data-ttu-id="e7bdf-107">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="e7bdf-107">cref = "`member`"</span></span>

  <span data-ttu-id="e7bdf-108">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-108">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="e7bdf-109">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-109">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="e7bdf-110">Setzen Sie *member* in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="e7bdf-110">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="e7bdf-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7bdf-111">Remarks</span></span>

<span data-ttu-id="e7bdf-112">Mit dem `<see>`-Tag kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-112">The `<see>` tag lets you specify a link from within text.</span></span> <span data-ttu-id="e7bdf-113">Verwenden Sie [\<seealso>](./seealso.md), um anzugeben, dass Text in einen Abschnitt „Siehe auch“ eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-113">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="e7bdf-114">Verwenden Sie das [cref-Attribut](./cref-attribute.md), um interne Links zu Dokumentationsseiten für Codeelemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-114">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span> <span data-ttu-id="e7bdf-115">Außerdem ist ``href`` ein gültiges Attribut, das als Hyperlink fungiert.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-115">Also, ``href`` is a valid Attribute that will function as a hyperlink.</span></span>

<span data-ttu-id="e7bdf-116">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="e7bdf-117">Im folgenden Beispiel wird ein `<see>`-Tag innerhalb eines zusammenfassenden Abschnitts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-117">The following example shows a `<see>` tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="e7bdf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7bdf-118">See also</span></span>

- [<span data-ttu-id="e7bdf-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e7bdf-119">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="e7bdf-120">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="e7bdf-120">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
