---
title: <see> – C#-Programmierhandbuch
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
ms.openlocfilehash: 17d1d344b9a27ffd4995fa4849ee6d5ce7f90f29
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789700"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="467ec-102">\<see> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="467ec-102">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="467ec-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="467ec-103">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="467ec-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="467ec-104">Parameters</span></span>

- <span data-ttu-id="467ec-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="467ec-105">cref = " `member`"</span></span>

  <span data-ttu-id="467ec-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="467ec-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="467ec-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="467ec-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="467ec-108">Setzen Sie *member* in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="467ec-108">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="467ec-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="467ec-109">Remarks</span></span>

<span data-ttu-id="467ec-110">Mit dem \<see>-Tag kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="467ec-110">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="467ec-111">Verwenden Sie [\<seealso>](./seealso.md), um anzugeben, dass Text in einen Abschnitt „Siehe auch“ eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="467ec-111">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="467ec-112">Verwenden Sie das [cref-Attribut](./cref-attribute.md), um interne Links zu Dokumentationsseiten für Codeelemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="467ec-112">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="467ec-113">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="467ec-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="467ec-114">Im folgenden Beispiel wird ein \<see>-Tag innerhalb eines zusammenfassenden Abschnitts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="467ec-114">The following example shows a \<see> tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="467ec-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="467ec-115">See also</span></span>

- [<span data-ttu-id="467ec-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="467ec-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="467ec-117">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="467ec-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
