---
title: Empfohlene Tags für Dokumentationskommentare – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: ac8629dacbb8c1fde1f55468e5d2aeaf78cfe017
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928028"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="a5315-102">Empfohlene Tags für Dokumentationskommentare (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a5315-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="a5315-103">Der C#-Compiler verarbeitet Dokumentationskommentare in Ihrem Code und formatiert diese als XML in einer Datei, deren Namen Sie in der Befehlszeilenoption **/doc** angeben.</span><span class="sxs-lookup"><span data-stu-id="a5315-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="a5315-104">Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie z. B. [DocFX](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5315-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="a5315-105">Tags werden auf der Basis von Codekonstrukten wie Typen und Typmembern verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a5315-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5315-106">Dokumentationskommentare können nicht auf einen Namespace angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a5315-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="a5315-107">Der Compiler verarbeitet alle Tags, die gültige XML sind.</span><span class="sxs-lookup"><span data-stu-id="a5315-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="a5315-108">Die folgenden Tags stellen allgemein verwendete Funktionen in der Benutzerdokumentation bereit.</span><span class="sxs-lookup"><span data-stu-id="a5315-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="a5315-109">Tags</span><span class="sxs-lookup"><span data-stu-id="a5315-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="a5315-110">\<c></span><span class="sxs-lookup"><span data-stu-id="a5315-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="a5315-111">\<para></span><span class="sxs-lookup"><span data-stu-id="a5315-111">\<para></span></span>](./para.md)|<span data-ttu-id="a5315-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="a5315-112">[\<see>](./see.md)\*</span></span>|  
|[<span data-ttu-id="a5315-113">\<code></span><span class="sxs-lookup"><span data-stu-id="a5315-113">\<code></span></span>](./code.md)|<span data-ttu-id="a5315-114">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="a5315-114">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="a5315-115">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="a5315-115">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="a5315-116">\<example></span><span class="sxs-lookup"><span data-stu-id="a5315-116">\<example></span></span>](./example.md)|[<span data-ttu-id="a5315-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="a5315-117">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="a5315-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="a5315-118">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="a5315-119">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="a5315-119">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="a5315-120">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="a5315-120">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="a5315-121">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="a5315-121">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="a5315-122">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="a5315-122">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="a5315-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="a5315-123">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="a5315-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="a5315-124">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="a5315-125">\<list></span><span class="sxs-lookup"><span data-stu-id="a5315-125">\<list></span></span>](./list.md)|[<span data-ttu-id="a5315-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="a5315-126">\<returns></span></span>](./returns.md)|[<span data-ttu-id="a5315-127">\<value></span><span class="sxs-lookup"><span data-stu-id="a5315-127">\<value></span></span>](./value.md)|  
  
 <span data-ttu-id="a5315-128">(\* gibt an, dass der Compiler die Syntax überprüft.)</span><span class="sxs-lookup"><span data-stu-id="a5315-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="a5315-129">Wenn Sie möchten, dass im Text eines Dokumentationskommentars spitze Klammern erscheinen, verwenden Sie die HTML-Codierung für `<` und `>`: `&lt;` bzw. `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="a5315-129">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="a5315-130">Diese Codierung wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a5315-130">This encoding is shown in the following example:</span></span>
  
```csharp  
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```
  
## <a name="see-also"></a><span data-ttu-id="a5315-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5315-131">See also</span></span>

- [<span data-ttu-id="a5315-132">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a5315-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a5315-133">/doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a5315-133">/doc (C# Compiler Options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="a5315-134">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="a5315-134">XML Documentation Comments</span></span>](./index.md)
