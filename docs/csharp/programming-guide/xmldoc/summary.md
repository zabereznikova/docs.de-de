---
title: <summary> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <summary> , das zur Beschreibung eines Typs oder Typmembers verwendet wird. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: f9243e598aaf0c12dd48b48045f461b4b307c18f
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380604"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="fa549-105">\<summary> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fa549-105">\<summary> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="fa549-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa549-106">Syntax</span></span>

```xml
<summary>description</summary>
```

## <a name="parameters"></a><span data-ttu-id="fa549-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa549-107">Parameters</span></span>

- `description`

  <span data-ttu-id="fa549-108">Eine Übersicht des Objekts.</span><span class="sxs-lookup"><span data-stu-id="fa549-108">A summary of the object.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa549-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa549-109">Remarks</span></span>

<span data-ttu-id="fa549-110">Das `<summary>`-Tag sollte für die Beschreibung eines Typs oder Typmembers verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa549-110">The `<summary>` tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="fa549-111">Verwenden Sie [\<remarks>](./remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa549-111">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="fa549-112">Verwenden Sie das [cref-Attribut](./cref-attribute.md), um Dokumentationswerkzeuge wie [DocFX](https://dotnet.github.io/docfx/) und [Sandcastle](https://github.com/EWSoftware/SHFB) zum Erstellen von internen Links zu Dokumentationsseiten für Codeelemente zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fa549-112">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="fa549-113">Der Text für das `<summary>`-Tag stellt die einzige Informationsquelle in Bezug auf den Typ in IntelliSense dar und wird auch im Fenster „Objektkatalog“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa549-113">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>

<span data-ttu-id="fa549-114">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fa549-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="fa549-115">Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie z. B. [DocFX](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa549-115">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

## <a name="example"></a><span data-ttu-id="fa549-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa549-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

<span data-ttu-id="fa549-117">Das vorherige Beispiel erzeugt folgende XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="fa549-117">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>YourNamespace</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            text for class TestClass
        </member>
        <member name="M:TestClass.DoWork(System.Int32)">
            <summary>DoWork is a method in the TestClass class.
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>
            </summary>
            <seealso cref="M:TestClass.Main"/>
        </member>
        <member name="M:TestClass.Main">
            text for Main
        </member>
    </members>
</doc>
```

## <a name="example"></a><span data-ttu-id="fa549-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa549-118">Example</span></span>

<span data-ttu-id="fa549-119">Das folgende Beispiel stellt dar, wie Sie einen `cref`-Verweis auf generische Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa549-119">The following example shows how to make a `cref` reference to a generic type.</span></span>

[!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]

<span data-ttu-id="fa549-120">Das vorherige Beispiel erzeugt folgende XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="fa549-120">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:A">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:B">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:C`1">
            <summary cref="T:A">
            </summary>
            <typeparam name="T"></typeparam>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="fa549-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa549-121">See also</span></span>

- [<span data-ttu-id="fa549-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fa549-122">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="fa549-123">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="fa549-123">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
