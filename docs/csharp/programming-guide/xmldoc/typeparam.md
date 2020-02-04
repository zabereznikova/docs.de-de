---
title: <typeparam> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 867ecacf58f95533395ded203a8f17bc92558ccf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793363"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="6138c-102">\<typeparam> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6138c-102">\<typeparam> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="6138c-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="6138c-103">Syntax</span></span>

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a><span data-ttu-id="6138c-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="6138c-104">Parameters</span></span>

- `name`

  <span data-ttu-id="6138c-105">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="6138c-105">The name of the type parameter.</span></span> <span data-ttu-id="6138c-106">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="6138c-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="6138c-107">Eine Beschreibung für den Typparameter.</span><span class="sxs-lookup"><span data-stu-id="6138c-107">A description for the type parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="6138c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6138c-108">Remarks</span></span>

<span data-ttu-id="6138c-109">Die `<typeparam>` -Tag sollte im Kommentar für einen generischen Typ oder eine Methodendeklaration verwendet werden, um einen Typparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="6138c-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="6138c-110">Fügen Sie ein Tag für jeden Typparameter des generischen Typs oder der Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="6138c-110">Add a tag for each type parameter of the generic type or method.</span></span>

<span data-ttu-id="6138c-111">Weitere Informationen finden Sie unter [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="6138c-111">For more information, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="6138c-112">Der Text für die `<typeparam>` Tag wird in IntelliSense angezeigt werden, dem [Objekt Browserfenster](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) Webbericht für Codekommentare.</span><span class="sxs-lookup"><span data-stu-id="6138c-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>

<span data-ttu-id="6138c-113">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6138c-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="6138c-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6138c-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="6138c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6138c-115">See also</span></span>

- [<span data-ttu-id="6138c-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6138c-116">C# reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="6138c-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6138c-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="6138c-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="6138c-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
