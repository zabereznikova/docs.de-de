---
title: <value> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 120805346672738e614743ab8c98388b8dbac0f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793351"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="26476-102">\<value> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="26476-102">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="26476-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="26476-103">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="26476-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="26476-104">Parameters</span></span>

- `property-description`

  <span data-ttu-id="26476-105">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="26476-105">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="26476-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26476-106">Remarks</span></span>

<span data-ttu-id="26476-107">Mit dem \<value>-Tag können Sie den Wert beschreiben, den eine Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="26476-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="26476-108">Beachten Sie, dass beim Hinzufügen einer Eigenschaft mithilfe des Code-Assistenten in der Entwicklungsumgebung von Visual Studio .NET der neuen Eigenschaft ein [\<summary>](./summary.md)-Tag hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="26476-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="26476-109">Sie sollten dann manuell ein \<value>-Tag hinzufügen, um den Wert zu beschreiben, den die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="26476-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>

<span data-ttu-id="26476-110">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="26476-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="26476-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26476-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="26476-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26476-112">See also</span></span>

- [<span data-ttu-id="26476-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="26476-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="26476-114">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="26476-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
