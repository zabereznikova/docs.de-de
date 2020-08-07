---
title: <remarks> – C#-Programmierhandbuch
description: 'Erfahren Sie mehr über das XML-Tag <remarks> ein. Dieses Tag wird verwendet, um Informationen zu einem Typ hinzuzufügen und die hiermit angegebenen Informationen zu ergänzen: <summary>.'
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: d38905d100e24158e7a1412f6be9f01a7ced2382
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381501"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="63c7f-106">\<remarks> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="63c7f-106">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="63c7f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="63c7f-107">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="63c7f-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="63c7f-108">Parameters</span></span>

- `Description`

  <span data-ttu-id="63c7f-109">Eine Beschreibung des Members</span><span class="sxs-lookup"><span data-stu-id="63c7f-109">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="63c7f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="63c7f-110">Remarks</span></span>

<span data-ttu-id="63c7f-111">Das Tag `<remarks>` wird verwendet, um Informationen zu einem Typ hinzuzufügen. Dadurch werden die mit [\<summary>](./summary.md) angegebenen Informationen ergänzt.</span><span class="sxs-lookup"><span data-stu-id="63c7f-111">The `<remarks>` tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="63c7f-112">Diese Informationen werden im Fenster des Objektkatalogs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63c7f-112">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="63c7f-113">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="63c7f-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="63c7f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63c7f-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="63c7f-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63c7f-115">See also</span></span>

- [<span data-ttu-id="63c7f-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="63c7f-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="63c7f-117">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="63c7f-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
