---
title: Empfohlene Tags für Dokumentationskommentare – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: d17ff0b78d8ae40916447e8e12da7948a21e5717
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523366"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="bdab7-102">Empfohlene Tags für Dokumentationskommentare (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="bdab7-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="bdab7-103">Der C#-Compiler verarbeitet Dokumentationskommentare in Ihrem Code und formatiert diese als XML in einer Datei, deren Namen Sie in der Befehlszeilenoption **/doc** angeben.</span><span class="sxs-lookup"><span data-stu-id="bdab7-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="bdab7-104">Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie z. B. [DocFX](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="bdab7-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="bdab7-105">Tags werden auf der Basis von Codekonstrukten wie Typen und Typmembern verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="bdab7-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bdab7-106">Dokumentationskommentare können nicht auf einen Namespace angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="bdab7-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="bdab7-107">Der Compiler verarbeitet alle Tags, die gültige XML sind.</span><span class="sxs-lookup"><span data-stu-id="bdab7-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="bdab7-108">Die folgenden Tags stellen allgemein verwendete Funktionen in der Benutzerdokumentation bereit.</span><span class="sxs-lookup"><span data-stu-id="bdab7-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="bdab7-109">Tags</span><span class="sxs-lookup"><span data-stu-id="bdab7-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="bdab7-110">\<c></span><span class="sxs-lookup"><span data-stu-id="bdab7-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="bdab7-111">\<para></span><span class="sxs-lookup"><span data-stu-id="bdab7-111">\<para></span></span>](./para.md)|<span data-ttu-id="bdab7-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="bdab7-112">[\<see>](./see.md)\*</span></span>|  
|[<span data-ttu-id="bdab7-113">\<code></span><span class="sxs-lookup"><span data-stu-id="bdab7-113">\<code></span></span>](./code.md)|<span data-ttu-id="bdab7-114">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="bdab7-114">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="bdab7-115">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="bdab7-115">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="bdab7-116">\<example></span><span class="sxs-lookup"><span data-stu-id="bdab7-116">\<example></span></span>](./example.md)|[<span data-ttu-id="bdab7-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="bdab7-117">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="bdab7-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="bdab7-118">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="bdab7-119">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="bdab7-119">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="bdab7-120">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="bdab7-120">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="bdab7-121">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="bdab7-121">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="bdab7-122">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="bdab7-122">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="bdab7-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="bdab7-123">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="bdab7-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="bdab7-124">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="bdab7-125">\<list></span><span class="sxs-lookup"><span data-stu-id="bdab7-125">\<list></span></span>](./list.md)|[<span data-ttu-id="bdab7-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="bdab7-126">\<returns></span></span>](./returns.md)|[<span data-ttu-id="bdab7-127">\<value></span><span class="sxs-lookup"><span data-stu-id="bdab7-127">\<value></span></span>](./value.md)|  
  
 <span data-ttu-id="bdab7-128">(\* gibt an, dass der Compiler die Syntax überprüft.)</span><span class="sxs-lookup"><span data-stu-id="bdab7-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="bdab7-129">Wenn Sie möchten, dass im Text eines Dokumentationskommentars spitze Klammern erscheinen, verwenden Sie die HTML-Codierung für `<` und `>`: `&lt;` bzw. `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="bdab7-129">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="bdab7-130">Diese Codierung wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="bdab7-130">This encoding is shown in the following example:</span></span>
  
```csharp  
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```
  
## <a name="see-also"></a><span data-ttu-id="bdab7-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdab7-131">See also</span></span>

- [<span data-ttu-id="bdab7-132">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bdab7-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bdab7-133">-doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="bdab7-133">-doc (C# Compiler Options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="bdab7-134">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="bdab7-134">XML Documentation Comments</span></span>](./index.md)
