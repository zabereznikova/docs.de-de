---
title: <typeparam> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <typeparam> ein. Dieses Tag wird im Kommentar für eine generische Typ- oder Methodendeklaration verwendet, um einen Typparameter zu beschreiben.
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 5e5333e384e8c77b500f74ab7c6038146df6e2c0
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380786"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="19864-105">\<typeparam> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="19864-105">\<typeparam> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="19864-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="19864-106">Syntax</span></span>

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a><span data-ttu-id="19864-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="19864-107">Parameters</span></span>

- `name`

  <span data-ttu-id="19864-108">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="19864-108">The name of the type parameter.</span></span> <span data-ttu-id="19864-109">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="19864-109">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="19864-110">Eine Beschreibung für den Typparameter.</span><span class="sxs-lookup"><span data-stu-id="19864-110">A description for the type parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="19864-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19864-111">Remarks</span></span>

<span data-ttu-id="19864-112">Die `<typeparam>` -Tag sollte im Kommentar für einen generischen Typ oder eine Methodendeklaration verwendet werden, um einen Typparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="19864-112">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="19864-113">Fügen Sie ein Tag für jeden Typparameter des generischen Typs oder der Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="19864-113">Add a tag for each type parameter of the generic type or method.</span></span>

<span data-ttu-id="19864-114">Weitere Informationen finden Sie unter [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="19864-114">For more information, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="19864-115">Der Text für die `<typeparam>` Tag wird in IntelliSense angezeigt werden, dem [Objekt Browserfenster](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) Webbericht für Codekommentare.</span><span class="sxs-lookup"><span data-stu-id="19864-115">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>

<span data-ttu-id="19864-116">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="19864-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="19864-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19864-117">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="19864-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19864-118">See also</span></span>

- [<span data-ttu-id="19864-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="19864-119">C# reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="19864-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="19864-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="19864-121">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="19864-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
