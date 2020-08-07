---
title: <list> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <list> ein. Dieses Tag wird verwendet, um Tabellen und die zugehörige Definition sowie Aufzählungen oder nummerierte Listen mithilfe von item-Blöcken zu erstellen.
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 361c2e6f343554a9b8519c3b2e41219b209e682d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381865"
---
# <a name="list-c-programming-guide"></a><span data-ttu-id="7492c-105">\<list> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="7492c-105">\<list> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="7492c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7492c-106">Syntax</span></span>

```xml
<list type="bullet|number|table">
    <listheader>
        <term>term</term>
        <description>description</description>
    </listheader>
    <item>
        <term>term</term>
        <description>description</description>
    </item>
</list>
```

## <a name="parameters"></a><span data-ttu-id="7492c-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="7492c-107">Parameters</span></span>

- `term`

  <span data-ttu-id="7492c-108">Ein zu definierender Begriff, der in `description` definiert wird.</span><span class="sxs-lookup"><span data-stu-id="7492c-108">A term to define, which will be defined in `description`.</span></span>

- `description`

  <span data-ttu-id="7492c-109">Entweder ein Element einer Aufzählung oder nummerierten Liste oder die Definition eines `term`.</span><span class="sxs-lookup"><span data-stu-id="7492c-109">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7492c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7492c-110">Remarks</span></span>

<span data-ttu-id="7492c-111">Der `<listheader>`-Block wird verwendet, um die Überschriftenzeile einer Tabelle oder einer Definitionsliste zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7492c-111">The `<listheader>` block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="7492c-112">Bei der Definition einer Tabelle müssen Sie nur einen Eintrag für „term“ in der Überschrift angeben.</span><span class="sxs-lookup"><span data-stu-id="7492c-112">When defining a table, you only need to supply an entry for term in the heading.</span></span>

<span data-ttu-id="7492c-113">Jedes Element der Liste wird mit einem `<item>`-Block angegeben.</span><span class="sxs-lookup"><span data-stu-id="7492c-113">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="7492c-114">Beim Erstellen einer Definitionsliste müssen Sie sowohl `term` als auch `description` angeben.</span><span class="sxs-lookup"><span data-stu-id="7492c-114">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="7492c-115">Für eine Tabelle, eine Auflistung oder eine nummerierte Liste muss jedoch nur ein Eintrag für `description` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7492c-115">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>

<span data-ttu-id="7492c-116">Eine Liste oder Tabelle kann so viele `<item>`-Blöcke besitzen wie nötig.</span><span class="sxs-lookup"><span data-stu-id="7492c-116">A list or table can have as many `<item>` blocks as needed.</span></span>

<span data-ttu-id="7492c-117">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7492c-117">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="7492c-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7492c-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]

## <a name="see-also"></a><span data-ttu-id="7492c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7492c-119">See also</span></span>

- [<span data-ttu-id="7492c-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7492c-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="7492c-121">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="7492c-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
