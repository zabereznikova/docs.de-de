---
title: <remarks> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 739027786e02e559d86f990bf614e261b497c76f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287284"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="43699-102">\<remarks> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="43699-102">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="43699-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="43699-103">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="43699-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="43699-104">Parameters</span></span>

- `Description`

  <span data-ttu-id="43699-105">Eine Beschreibung des Members</span><span class="sxs-lookup"><span data-stu-id="43699-105">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="43699-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43699-106">Remarks</span></span>

<span data-ttu-id="43699-107">Das Tag `<remarks>` wird verwendet, um Informationen zu einem Typ hinzuzufügen. Dadurch werden die mit [\<summary>](./summary.md) angegebenen Informationen ergänzt.</span><span class="sxs-lookup"><span data-stu-id="43699-107">The `<remarks>` tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="43699-108">Diese Informationen werden im Fenster des Objektkatalogs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="43699-108">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="43699-109">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="43699-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="43699-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43699-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="43699-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43699-111">See also</span></span>

- [<span data-ttu-id="43699-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="43699-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="43699-113">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="43699-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
