---
title: <typeparamref> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <typeparamref>. Dieses Tag ermöglicht es Nutzern der Dokumentationsdatei, ein Wort auf unterschiedliche Weise zu formatieren, z. B. kursiv.
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: a39e896f1242452c7bcc94faa1e7ef3086ae2149
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380721"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="9bc48-104">\<typeparamref> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9bc48-104">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="9bc48-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9bc48-105">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="9bc48-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9bc48-106">Parameters</span></span>

- `name`

  <span data-ttu-id="9bc48-107">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="9bc48-107">The name of the type parameter.</span></span> <span data-ttu-id="9bc48-108">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="9bc48-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="9bc48-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9bc48-109">Remarks</span></span>

<span data-ttu-id="9bc48-110">Weitere Informationen zu den Typparametern in generischen Typen und Methoden, finden Sie unter [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="9bc48-110">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="9bc48-111">Verwenden Sie dieses Tag, um Consumern der Dokumentationsdatei zu ermöglichen, das Wort auf unterschiedliche Weise zu formatieren, z.B. in Kursivschrift.</span><span class="sxs-lookup"><span data-stu-id="9bc48-111">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="9bc48-112">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9bc48-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="9bc48-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bc48-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="9bc48-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bc48-114">See also</span></span>

- [<span data-ttu-id="9bc48-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9bc48-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="9bc48-116">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="9bc48-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
