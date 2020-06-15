---
title: <summary> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: f6984c60e6a7132e94c5c91837535484b12f93c5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590617"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="19045-102">\<summary> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="19045-102">\<summary> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="19045-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="19045-103">Syntax</span></span>

```xml
<summary>description</summary>
```

## <a name="parameters"></a><span data-ttu-id="19045-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="19045-104">Parameters</span></span>

- `description`

  <span data-ttu-id="19045-105">Eine Übersicht des Objekts.</span><span class="sxs-lookup"><span data-stu-id="19045-105">A summary of the object.</span></span>

## <a name="remarks"></a><span data-ttu-id="19045-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19045-106">Remarks</span></span>

<span data-ttu-id="19045-107">Das `<summary>`-Tag sollte für die Beschreibung eines Typs oder Typmembers verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19045-107">The `<summary>` tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="19045-108">Verwenden Sie [\<remarks>](./remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="19045-108">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="19045-109">Verwenden Sie das [cref-Attribut](./cref-attribute.md), um Dokumentationswerkzeuge wie [DocFX](https://dotnet.github.io/docfx/) und [Sandcastle](https://github.com/EWSoftware/SHFB) zum Erstellen von internen Links zu Dokumentationsseiten für Codeelemente zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="19045-109">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="19045-110">Der Text für das `<summary>`-Tag stellt die einzige Informationsquelle in Bezug auf den Typ in IntelliSense dar und wird auch im Fenster „Objektkatalog“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="19045-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>

<span data-ttu-id="19045-111">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="19045-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="19045-112">Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie z. B. [DocFX](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="19045-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

## <a name="example"></a><span data-ttu-id="19045-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19045-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

<span data-ttu-id="19045-114">Das vorherige Beispiel erzeugt folgende XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="19045-114">The previous example produces the following XML file.</span></span>

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

## <a name="example"></a><span data-ttu-id="19045-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19045-115">Example</span></span>

<span data-ttu-id="19045-116">Das folgende Beispiel stellt dar, wie Sie einen `cref`-Verweis auf generische Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="19045-116">The following example shows how to make a `cref` reference to a generic type.</span></span>

[!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]

<span data-ttu-id="19045-117">Das vorherige Beispiel erzeugt folgende XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="19045-117">The previous example produces the following XML file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="19045-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19045-118">See also</span></span>

- [<span data-ttu-id="19045-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="19045-119">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="19045-120">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="19045-120">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
