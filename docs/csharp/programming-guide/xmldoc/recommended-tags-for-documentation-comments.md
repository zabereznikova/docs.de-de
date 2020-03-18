---
title: Empfohlene Tags für Dokumentationskommentare – C#-Programmierhandbuch
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: c746615d0d7a7a3058fbe2f8506a7a7c5c4a8779
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789723"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="01563-102">Empfohlene Tags für Dokumentationskommentare (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="01563-102">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="01563-103">Der C#-Compiler verarbeitet Dokumentationskommentare in Ihrem Code und formatiert diese als XML in einer Datei, deren Namen Sie in der Befehlszeilenoption **/doc** angeben.</span><span class="sxs-lookup"><span data-stu-id="01563-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="01563-104">Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie z. B. [DocFX](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="01563-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="01563-105">Tags werden auf der Basis von Codekonstrukten wie Typen und Typmembern verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="01563-105">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="01563-106">Dokumentationskommentare können nicht auf einen Namespace angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="01563-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="01563-107">Der Compiler verarbeitet alle Tags, die gültige XML sind.</span><span class="sxs-lookup"><span data-stu-id="01563-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="01563-108">Die folgenden Tags stellen allgemein verwendete Funktionen in der Benutzerdokumentation bereit.</span><span class="sxs-lookup"><span data-stu-id="01563-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="01563-109">Tags</span><span class="sxs-lookup"><span data-stu-id="01563-109">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[<span data-ttu-id="01563-110">\<c></span><span class="sxs-lookup"><span data-stu-id="01563-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="01563-111">\<para></span><span class="sxs-lookup"><span data-stu-id="01563-111">\<para></span></span>](./para.md)|<span data-ttu-id="01563-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="01563-112">[\<see>](./see.md)\*</span></span>|[<span data-ttu-id="01563-113">\<value></span><span class="sxs-lookup"><span data-stu-id="01563-113">\<value></span></span>](./value.md)  
|[<span data-ttu-id="01563-114">\<code></span><span class="sxs-lookup"><span data-stu-id="01563-114">\<code></span></span>](./code.md)|<span data-ttu-id="01563-115">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="01563-115">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="01563-116">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="01563-116">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="01563-117">\<example></span><span class="sxs-lookup"><span data-stu-id="01563-117">\<example></span></span>](./example.md)|[<span data-ttu-id="01563-118">\<paramref></span><span class="sxs-lookup"><span data-stu-id="01563-118">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="01563-119">\<summary></span><span class="sxs-lookup"><span data-stu-id="01563-119">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="01563-120">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="01563-120">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="01563-121">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="01563-121">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="01563-122">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="01563-122">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="01563-123">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="01563-123">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="01563-124">\<remarks></span><span class="sxs-lookup"><span data-stu-id="01563-124">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="01563-125">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="01563-125">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="01563-126">\<list></span><span class="sxs-lookup"><span data-stu-id="01563-126">\<list></span></span>](./list.md)|[<span data-ttu-id="01563-127">\<inheritdoc></span><span class="sxs-lookup"><span data-stu-id="01563-127">\<inheritdoc></span></span>](./inheritdoc.md)|[<span data-ttu-id="01563-128">\<returns></span><span class="sxs-lookup"><span data-stu-id="01563-128">\<returns></span></span>](./returns.md)|
  
<span data-ttu-id="01563-129">(\* gibt an, dass der Compiler die Syntax überprüft.)</span><span class="sxs-lookup"><span data-stu-id="01563-129">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="01563-130">Wenn Sie möchten, dass im Text eines Dokumentationskommentars spitze Klammern erscheinen, verwenden Sie die HTML-Codierung für `<` und `>`: `&lt;` bzw. `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="01563-130">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="01563-131">Diese Codierung wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="01563-131">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="01563-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01563-132">See also</span></span>

- [<span data-ttu-id="01563-133">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="01563-133">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="01563-134">-doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="01563-134">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="01563-135">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="01563-135">XML documentation comments</span></span>](./index.md)
