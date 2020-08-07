---
title: <returns> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <returns> ein. Dieses Tag wird im Kommentar für eine Methodendeklaration verwendet, um den Rückgabewert zu beschreiben.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381397"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="a9302-105">\<returns> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a9302-105">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="a9302-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9302-106">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="a9302-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9302-107">Parameters</span></span>

- `description`

  <span data-ttu-id="a9302-108">Eine Beschreibung des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="a9302-108">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9302-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a9302-109">Remarks</span></span>

<span data-ttu-id="a9302-110">Das `<returns>`-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um den Rückgabewert zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a9302-110">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="a9302-111">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a9302-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="a9302-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9302-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="a9302-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9302-113">See also</span></span>

- [<span data-ttu-id="a9302-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a9302-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="a9302-115">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="a9302-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
