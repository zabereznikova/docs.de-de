---
title: <typeparamref> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 266eadad322fd3c4167c7a911cb57ef1e1333012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789658"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="cb53d-102">\<typeparamref> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="cb53d-102">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="cb53d-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb53d-103">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="cb53d-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="cb53d-104">Parameters</span></span>

- `name`

  <span data-ttu-id="cb53d-105">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="cb53d-105">The name of the type parameter.</span></span> <span data-ttu-id="cb53d-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="cb53d-106">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="cb53d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cb53d-107">Remarks</span></span>

<span data-ttu-id="cb53d-108">Weitere Informationen zu den Typparametern in generischen Typen und Methoden, finden Sie unter [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="cb53d-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="cb53d-109">Verwenden Sie dieses Tag, um Consumern der Dokumentationsdatei zu ermöglichen, das Wort auf unterschiedliche Weise zu formatieren, z.B. in Kursivschrift.</span><span class="sxs-lookup"><span data-stu-id="cb53d-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="cb53d-110">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="cb53d-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="cb53d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb53d-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="cb53d-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb53d-112">See also</span></span>

- [<span data-ttu-id="cb53d-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cb53d-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="cb53d-114">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="cb53d-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
