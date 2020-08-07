---
title: <param> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <param> ein. Dieses Tag wird im Kommentar für eine Methodendeklaration verwendet, um einen der Methodenparameter zu beschreiben.
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: a9e3b2e86528afcbe1330788e248f0143efb5c1b
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381553"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="8c9b9-105">\<param> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8c9b9-105">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="8c9b9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c9b9-106">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="8c9b9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c9b9-107">Parameters</span></span>

- `name`

  <span data-ttu-id="8c9b9-108">Der Name eines Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="8c9b9-108">The name of a method parameter.</span></span> <span data-ttu-id="8c9b9-109">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="8c9b9-109">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="8c9b9-110">Eine Beschreibung für den Parameter</span><span class="sxs-lookup"><span data-stu-id="8c9b9-110">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c9b9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c9b9-111">Remarks</span></span>

<span data-ttu-id="8c9b9-112">Das `<param>`-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="8c9b9-112">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="8c9b9-113">Verwenden Sie mehrere `<param>`-Tags, um mehrere Parameter zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="8c9b9-113">To document multiple parameters, use multiple `<param>` tags.</span></span>

<span data-ttu-id="8c9b9-114">Der Text für das `<param>`-Tag wird in IntelliSense, dem Objektkatalog und im Webbericht über Codekommentare angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c9b9-114">The text for the `<param>` tag is displayed in IntelliSense, the Object Browser, and the Code Comment Web Report.</span></span>

<span data-ttu-id="8c9b9-115">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8c9b9-115">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="8c9b9-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c9b9-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="8c9b9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c9b9-117">See also</span></span>

- [<span data-ttu-id="8c9b9-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8c9b9-118">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="8c9b9-119">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="8c9b9-119">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
