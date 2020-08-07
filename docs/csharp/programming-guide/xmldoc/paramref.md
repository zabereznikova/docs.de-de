---
title: <paramref> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <paramref>. Mit diesem Tag können Sie angeben, dass ein Wort im Code ein Parameter ist.
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 133f43abfaf349806404d6d37fb472e3145c51b7
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381839"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="2bd55-104">\<paramref> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2bd55-104">\<paramref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="2bd55-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bd55-105">Syntax</span></span>

```xml
<paramref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="2bd55-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2bd55-106">Parameters</span></span>

- `name`

  <span data-ttu-id="2bd55-107">Der Name des Parameters, auf den verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2bd55-107">The name of the parameter to refer to.</span></span> <span data-ttu-id="2bd55-108">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="2bd55-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="2bd55-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2bd55-109">Remarks</span></span>

<span data-ttu-id="2bd55-110">Das Tag `<paramref>` bietet Ihnen eine Möglichkeit anzugeben, dass sich ein Wort in den Codekommentaren, z. B. in einem `<summary>`- oder `<remarks>`-Block, auf einen Parameter bezieht.</span><span class="sxs-lookup"><span data-stu-id="2bd55-110">The `<paramref>` tag gives you a way to indicate that a word in the code comments, for example in a `<summary>` or `<remarks>` block refers to a parameter.</span></span> <span data-ttu-id="2bd55-111">Die XML-Datei kann so verarbeitet werden, dass dieses Wort anders formatiert wird, z.B. fett oder kursiv.</span><span class="sxs-lookup"><span data-stu-id="2bd55-111">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>

<span data-ttu-id="2bd55-112">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2bd55-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="2bd55-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2bd55-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a><span data-ttu-id="2bd55-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2bd55-114">See also</span></span>

- [<span data-ttu-id="2bd55-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2bd55-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2bd55-116">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="2bd55-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
