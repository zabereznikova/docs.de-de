---
title: Empfohlene Tags für Dokumentationskommentare – C#-Programmierhandbuch
description: Erfahren Sie mehr über die empfohlenen Tags für Dokumentationskommentare. Hier finden Sie eine Liste der empfohlenen Tags sowie zusätzliche verfügbare Ressourcen.
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: 65bca6f979c5ffd91507b571a4f049377315192d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381514"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="c6074-104">Empfohlene Tags für Dokumentationskommentare (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c6074-104">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="c6074-105">Der C#-Compiler verarbeitet Dokumentationskommentare in Ihrem Code und formatiert diese als XML in einer Datei, deren Namen Sie in der Befehlszeilenoption **/doc** angeben.</span><span class="sxs-lookup"><span data-stu-id="c6074-105">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="c6074-106">Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie z. B. [DocFX](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6074-106">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="c6074-107">Tags werden auf der Basis von Codekonstrukten wie Typen und Typmembern verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c6074-107">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="c6074-108">Dokumentationskommentare können nicht auf einen Namespace angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6074-108">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="c6074-109">Der Compiler verarbeitet alle Tags, die gültige XML sind.</span><span class="sxs-lookup"><span data-stu-id="c6074-109">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="c6074-110">Die folgenden Tags stellen allgemein verwendete Funktionen in der Benutzerdokumentation bereit.</span><span class="sxs-lookup"><span data-stu-id="c6074-110">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="c6074-111">Tags</span><span class="sxs-lookup"><span data-stu-id="c6074-111">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[\<c>](./code-inline.md)|[\<para>](./para.md)|[\<see>](./see.md)*|[\<value>](./value.md)  
|[\<code>](./code.md)|[\<param>](./param.md)*|[\<seealso>](./seealso.md)*|  
|[\<example>](./example.md)|[\<paramref>](./paramref.md)|[\<summary>](./summary.md)|  
|[\<exception>](./exception.md)*|[\<permission>](./permission.md)*|[\<typeparam>](./typeparam.md)*|  
|[\<include>](./include.md)*|[\<remarks>](./remarks.md)|[\<typeparamref>](./typeparamref.md)|  
|[\<list>](./list.md)|[\<inheritdoc>](./inheritdoc.md)|[\<returns>](./returns.md)|
  
<span data-ttu-id="c6074-112">(\* gibt an, dass der Compiler die Syntax überprüft.)</span><span class="sxs-lookup"><span data-stu-id="c6074-112">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="c6074-113">Wenn Sie möchten, dass im Text eines Dokumentationskommentars spitze Klammern erscheinen, verwenden Sie die HTML-Codierung für `<` und `>`: `&lt;` bzw. `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="c6074-113">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="c6074-114">Diese Codierung wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c6074-114">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="c6074-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6074-115">See also</span></span>

- [<span data-ttu-id="c6074-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c6074-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="c6074-117">-doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="c6074-117">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="c6074-118">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="c6074-118">XML documentation comments</span></span>](./index.md)
