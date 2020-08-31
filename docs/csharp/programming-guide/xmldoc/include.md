---
title: <include> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <include> ein. Mit diesem Tag können Sie auf Kommentare in einer anderen Datei verweisen, die die Typen und Member in Ihrem Quellcode beschreiben.
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: d2de8fea17850685668766bc4ec6e64b1be77cce
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053190"
---
# <a name="include-c-programming-guide"></a><span data-ttu-id="90f3f-105">\<include> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="90f3f-105">\<include> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="90f3f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="90f3f-106">Syntax</span></span>

```xml
<include file='filename' path='tagpath[@name="id"]' />
```

## <a name="parameters"></a><span data-ttu-id="90f3f-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="90f3f-107">Parameters</span></span>

- `filename`

  <span data-ttu-id="90f3f-108">Der Name der XML-Datei, die die Dokumentation enthält.</span><span class="sxs-lookup"><span data-stu-id="90f3f-108">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="90f3f-109">Der Dateiname kann mit einem Pfad relativ zur Quellcodedatei qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="90f3f-109">The file name can be qualified with a path relative to the source code file.</span></span> <span data-ttu-id="90f3f-110">`filename` muss in einfache Anführungszeichen (‚‘) eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="90f3f-110">Enclose `filename` in single quotation marks (' ').</span></span>

- `tagpath`

  <span data-ttu-id="90f3f-111">Der Pfad der Tags in `filename`, der zum Tag `name` führt.</span><span class="sxs-lookup"><span data-stu-id="90f3f-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="90f3f-112">Der Pfad muss in einfache Anführungszeichen (‚‘) eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="90f3f-112">Enclose the path in single quotation marks (' ').</span></span>

- `name`

  <span data-ttu-id="90f3f-113">Der Namensbezeichner in dem Tag, das sich vor den Kommentaren befindet. `name` besitzt eine `id`.</span><span class="sxs-lookup"><span data-stu-id="90f3f-113">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>

- `id`

  <span data-ttu-id="90f3f-114">Die ID für das Tag, das sich vor den Kommentaren befindet.</span><span class="sxs-lookup"><span data-stu-id="90f3f-114">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="90f3f-115">Die ID muss in doppelte Anführungszeichen („“) eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="90f3f-115">Enclose the ID in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="90f3f-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90f3f-116">Remarks</span></span>

<span data-ttu-id="90f3f-117">Mit dem `<include>`-Tag können Sie auf Kommentare in einer anderen Datei verweisen, in denen die Typen und Member in Ihrem Quellcode beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="90f3f-117">The `<include>` tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="90f3f-118">Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei.</span><span class="sxs-lookup"><span data-stu-id="90f3f-118">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="90f3f-119">Durch das Ablegen der Dokumentation in einer separaten Datei können Sie die Quellcodeverwaltung unabhängig vom Quellcode auf die Dokumentation anwenden.</span><span class="sxs-lookup"><span data-stu-id="90f3f-119">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="90f3f-120">Eine Person kann die Quellcodedatei auschecken, eine andere die Dokumentationsdatei.</span><span class="sxs-lookup"><span data-stu-id="90f3f-120">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>

<span data-ttu-id="90f3f-121">Das `<include>`-Tag verwendet die XPath-Syntax.</span><span class="sxs-lookup"><span data-stu-id="90f3f-121">The `<include>` tag uses the XML XPath syntax.</span></span> <span data-ttu-id="90f3f-122">Weitere Anpassungsmöglichkeiten bei der Verwendung von `<include>` finden Sie in der XPath-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="90f3f-122">Refer to XPath documentation for ways to customize your `<include>` use.</span></span>

## <a name="example"></a><span data-ttu-id="90f3f-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90f3f-123">Example</span></span>

<span data-ttu-id="90f3f-124">Dies ist ein Beispiel einer Mehrfachdatei.</span><span class="sxs-lookup"><span data-stu-id="90f3f-124">This is a multifile example.</span></span> <span data-ttu-id="90f3f-125">Die folgende Datei ist die erste, die `<include>` verwendet.</span><span class="sxs-lookup"><span data-stu-id="90f3f-125">The following is the first file, which uses `<include>`.</span></span>

[!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]

<span data-ttu-id="90f3f-126">Die zweite Datei, *xml_include_tag.doc*, enthält die folgenden Dokumentationskommentare.</span><span class="sxs-lookup"><span data-stu-id="90f3f-126">The second file, *xml_include_tag.doc*, contains the following documentation comments.</span></span>

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a><span data-ttu-id="90f3f-127">Programmausgabe</span><span class="sxs-lookup"><span data-stu-id="90f3f-127">Program output</span></span>

<span data-ttu-id="90f3f-128">Die folgende Ausgabe wird generiert, wenn Sie die Klassen „Test“ und „Test2“ mit der folgenden Befehlszeile kompilieren: `-doc:DocFileName.xml.` In Visual Studio geben Sie die Option für XML-Dokumentkommentare im Buildbereich des Projekt-Designers an.</span><span class="sxs-lookup"><span data-stu-id="90f3f-128">The following output is generated when you compile the Test and Test2 classes with the following command line: `-doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="90f3f-129">Erkennt der C#-Compiler das `<include>`-Tag, so sucht er statt in der aktuellen Quelldatei in *xml_include_tag.doc* nach Dokumentationskommentaren.</span><span class="sxs-lookup"><span data-stu-id="90f3f-129">When the C# compiler sees the `<include>` tag, it searches for documentation comments in *xml_include_tag.doc* instead of the current source file.</span></span> <span data-ttu-id="90f3f-130">Der Compiler generiert dann *DocFileName.xml*. Dies ist die Datei, die von Dokumentationstools wie z. B. [Sandcastle](https://github.com/EWSoftware/SHFB) genutzt wird, um die endgültige Dokumentation zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="90f3f-130">The compiler then generates *DocFileName.xml*, and this is the file that is consumed by documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xml_include_tag</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```  
  
## <a name="see-also"></a><span data-ttu-id="90f3f-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90f3f-131">See also</span></span>

- [<span data-ttu-id="90f3f-132">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="90f3f-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="90f3f-133">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="90f3f-133">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
