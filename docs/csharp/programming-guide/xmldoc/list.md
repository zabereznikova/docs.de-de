---
title: <list> – C#-Programmierhandbuch
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
ms.openlocfilehash: cb289b26e9bc12d561892c421fb40da18d8c3513
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789749"
---
# <a name="list-c-programming-guide"></a><span data-ttu-id="486a0-102">\<list> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="486a0-102">\<list> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="486a0-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="486a0-103">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="486a0-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="486a0-104">Parameters</span></span>

- `term`

  <span data-ttu-id="486a0-105">Ein zu definierender Begriff, der in `description` definiert wird.</span><span class="sxs-lookup"><span data-stu-id="486a0-105">A term to define, which will be defined in `description`.</span></span>

- `description`

  <span data-ttu-id="486a0-106">Entweder ein Element einer Aufzählung oder nummerierten Liste oder die Definition eines `term`.</span><span class="sxs-lookup"><span data-stu-id="486a0-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="486a0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="486a0-107">Remarks</span></span>

<span data-ttu-id="486a0-108">Der \<listheader>-Block wird verwendet, um die Überschriftenzeile einer Tabelle oder einer Definitionsliste zu definieren.</span><span class="sxs-lookup"><span data-stu-id="486a0-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="486a0-109">Bei der Definition einer Tabelle müssen Sie nur einen Eintrag für „term“ in der Überschrift angeben.</span><span class="sxs-lookup"><span data-stu-id="486a0-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>

<span data-ttu-id="486a0-110">Jedes Element der Liste wird mit einem \<item>-Block angegeben.</span><span class="sxs-lookup"><span data-stu-id="486a0-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="486a0-111">Beim Erstellen einer Definitionsliste müssen Sie sowohl `term` als auch `description` angeben.</span><span class="sxs-lookup"><span data-stu-id="486a0-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="486a0-112">Für eine Tabelle, eine Auflistung oder eine nummerierte Liste muss jedoch nur ein Eintrag für `description` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="486a0-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>

<span data-ttu-id="486a0-113">Eine Liste oder Tabelle kann so viele \<item>-Blöcke besitzen wie nötig.</span><span class="sxs-lookup"><span data-stu-id="486a0-113">A list or table can have as many \<item> blocks as needed.</span></span>

<span data-ttu-id="486a0-114">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="486a0-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="486a0-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="486a0-115">Example</span></span>

[!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]

## <a name="see-also"></a><span data-ttu-id="486a0-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="486a0-116">See also</span></span>

- [<span data-ttu-id="486a0-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="486a0-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="486a0-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="486a0-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
