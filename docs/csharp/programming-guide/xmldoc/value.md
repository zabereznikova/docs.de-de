---
title: <value> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: bd6630a8d5894fda39ad289c8dd584f6d84e5490
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287193"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="6c756-102">\<value> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6c756-102">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="6c756-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c756-103">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="6c756-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c756-104">Parameters</span></span>

- `property-description`

  <span data-ttu-id="6c756-105">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6c756-105">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c756-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c756-106">Remarks</span></span>

<span data-ttu-id="6c756-107">Mit dem `<value>`-Tag können Sie den Wert beschreiben, den eine Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="6c756-107">The `<value>` tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="6c756-108">Beim Hinzufügen einer Eigenschaft über den Code-Assistenten in der Entwicklungsumgebung Visual Studio® .NET wird für die neue Eigenschaft ein [\<summary>](./summary.md)-Tag hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6c756-108">When you add a property via code wizard in the Visual Studio .NET development environment, it adds a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="6c756-109">Sie sollten dann manuell ein `<value>`-Tag für die Beschreibung des Werts hinzufügen, den die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="6c756-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>

<span data-ttu-id="6c756-110">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6c756-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="6c756-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c756-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="6c756-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c756-112">See also</span></span>

- [<span data-ttu-id="6c756-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6c756-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="6c756-114">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="6c756-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
