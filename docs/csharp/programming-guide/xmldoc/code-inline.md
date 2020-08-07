---
title: <c> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <c>. Dieses Tag kennzeichnet einzeiligen Text in einer Beschreibung als Code, während <code> indicates multiple lines.
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
ms.openlocfilehash: 78e59e1df4b096782e0a97b6d12c21c843a1cb21
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382021"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="2efdb-104">\<c> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2efdb-104">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="2efdb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2efdb-105">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="2efdb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2efdb-106">Parameters</span></span>

- `text`

  <span data-ttu-id="2efdb-107">Der Text, der als Code angegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="2efdb-107">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="2efdb-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2efdb-108">Remarks</span></span>

<span data-ttu-id="2efdb-109">Mit dem `<c>`-Tag kann angegeben werden, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2efdb-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="2efdb-110">Zum Angeben mehrerer Zeilen als Code wird [\<code>](./code.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="2efdb-110">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="2efdb-111">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2efdb-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="2efdb-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2efdb-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="2efdb-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2efdb-113">See also</span></span>

- [<span data-ttu-id="2efdb-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2efdb-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="2efdb-115">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="2efdb-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
