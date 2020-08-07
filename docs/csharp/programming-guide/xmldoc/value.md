---
title: <value> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <value> ein. Mit diesem Tag können Sie den Wert beschreiben, den eine Eigenschaft darstellt.
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: d8294b477d7067653c71d1ec2047a85a0bfe6d02
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380773"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="8516d-105">\<value> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8516d-105">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="8516d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8516d-106">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="8516d-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="8516d-107">Parameters</span></span>

- `property-description`

  <span data-ttu-id="8516d-108">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8516d-108">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="8516d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8516d-109">Remarks</span></span>

<span data-ttu-id="8516d-110">Mit dem `<value>`-Tag können Sie den Wert beschreiben, den eine Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="8516d-110">The `<value>` tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="8516d-111">Beim Hinzufügen einer Eigenschaft über den Code-Assistenten in der Entwicklungsumgebung Visual Studio® .NET wird für die neue Eigenschaft ein [\<summary>](./summary.md)-Tag hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8516d-111">When you add a property via code wizard in the Visual Studio .NET development environment, it adds a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="8516d-112">Sie sollten dann manuell ein `<value>`-Tag für die Beschreibung des Werts hinzufügen, den die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="8516d-112">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>

<span data-ttu-id="8516d-113">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8516d-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="8516d-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8516d-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="8516d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8516d-115">See also</span></span>

- [<span data-ttu-id="8516d-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8516d-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="8516d-117">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="8516d-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
