---
title: <example> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <example> ein. Mit diesem Tag können Sie ein Beispiel für die Verwendung einer Methode oder eines anderen Bibliotheksmembers angeben.
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: dd529e8f2a54cf9086d0d8c555dd1adb70b99126
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381527"
---
# <a name="example-c-programming-guide"></a><span data-ttu-id="bf408-105">\<example> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="bf408-105">\<example> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="bf408-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf408-106">Syntax</span></span>

```xml
<example>description</example>
```

## <a name="parameters"></a><span data-ttu-id="bf408-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="bf408-107">Parameters</span></span>

- `description`

  <span data-ttu-id="bf408-108">Eine Beschreibung des Codebeispiels.</span><span class="sxs-lookup"><span data-stu-id="bf408-108">A description of the code sample.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf408-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf408-109">Remarks</span></span>

<span data-ttu-id="bf408-110">Mit dem `<example>`-Tag kann ein Beispiel für die Verwendung einer Methode oder eines anderen Bibliothekmembers angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bf408-110">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="bf408-111">Dies schließt im Allgemeinen die Verwendung des [\<code>](./code.md)-Tags ein.</span><span class="sxs-lookup"><span data-stu-id="bf408-111">This commonly involves using the [\<code>](./code.md) tag.</span></span>

<span data-ttu-id="bf408-112">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="bf408-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="bf408-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf408-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a><span data-ttu-id="bf408-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf408-114">See also</span></span>

- [<span data-ttu-id="bf408-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bf408-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bf408-116">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="bf408-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
