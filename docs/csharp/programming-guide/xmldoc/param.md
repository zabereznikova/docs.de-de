---
title: <param> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d16070a82531519dd276b2ea999623017769d716
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789758"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="6461d-102">\<param> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6461d-102">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="6461d-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="6461d-103">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="6461d-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="6461d-104">Parameters</span></span>

- `name`

  <span data-ttu-id="6461d-105">Der Name eines Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="6461d-105">The name of a method parameter.</span></span> <span data-ttu-id="6461d-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="6461d-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="6461d-107">Eine Beschreibung für den Parameter</span><span class="sxs-lookup"><span data-stu-id="6461d-107">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="6461d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6461d-108">Remarks</span></span>

<span data-ttu-id="6461d-109">Das \<param>-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="6461d-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="6461d-110">Um mehrere Parameter zu dokumentieren, verwenden Sie mehrere \<param>-Tags.</span><span class="sxs-lookup"><span data-stu-id="6461d-110">To document multiple parameters, use multiple \<param> tags.</span></span>

<span data-ttu-id="6461d-111">Der Text für den \<param>-Tag wird in IntelliSense, dem Objektkatalog, und im Webbericht für Codekommentare angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6461d-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>

<span data-ttu-id="6461d-112">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6461d-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="6461d-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6461d-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="6461d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6461d-114">See also</span></span>

- [<span data-ttu-id="6461d-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6461d-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="6461d-116">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="6461d-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
