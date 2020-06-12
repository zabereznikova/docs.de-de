---
title: <c> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: a09bcd069e2f85f4a21736cb218c42c0e481d70b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287466"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="ed1c0-102">\<c> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ed1c0-102">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="ed1c0-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed1c0-103">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="ed1c0-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="ed1c0-104">Parameters</span></span>

- `text`

  <span data-ttu-id="ed1c0-105">Der Text, der als Code angegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed1c0-105">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed1c0-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed1c0-106">Remarks</span></span>

<span data-ttu-id="ed1c0-107">Mit dem `<c>`-Tag kann angegeben werden, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed1c0-107">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="ed1c0-108">Zum Angeben mehrerer Zeilen als Code wird [\<code>](./code.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed1c0-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="ed1c0-109">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ed1c0-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="ed1c0-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed1c0-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="ed1c0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed1c0-111">See also</span></span>

- [<span data-ttu-id="ed1c0-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ed1c0-112">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ed1c0-113">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="ed1c0-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
