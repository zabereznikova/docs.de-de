---
title: Empfohlene Tags für Dokumentationskommentare – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: fb4d8d4dde38d7cbe1b0434c290dd922b2e328a3
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245586"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="65b7d-102">Empfohlene Tags für Dokumentationskommentare (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="65b7d-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="65b7d-103">Der C#-Compiler verarbeitet Dokumentationskommentare in Ihrem Code und formatiert diese als XML in einer Datei, deren Namen Sie in der Befehlszeilenoption **/doc** angeben.</span><span class="sxs-lookup"><span data-stu-id="65b7d-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="65b7d-104">Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="65b7d-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="65b7d-105">Tags werden auf der Basis von Codekonstrukten wie Typen und Typmembern verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="65b7d-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65b7d-106">Dokumentationskommentare können nicht auf einen Namespace angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="65b7d-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="65b7d-107">Der Compiler verarbeitet alle Tags, die gültige XML sind.</span><span class="sxs-lookup"><span data-stu-id="65b7d-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="65b7d-108">Die folgenden Tags stellen allgemein verwendete Funktionen in der Benutzerdokumentation bereit.</span><span class="sxs-lookup"><span data-stu-id="65b7d-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="65b7d-109">Tags</span><span class="sxs-lookup"><span data-stu-id="65b7d-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="65b7d-110">\<c></span><span class="sxs-lookup"><span data-stu-id="65b7d-110">\<c></span></span>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[<span data-ttu-id="65b7d-111">\<para></span><span class="sxs-lookup"><span data-stu-id="65b7d-111">\<para></span></span>](../../../csharp/programming-guide/xmldoc/para.md)|<span data-ttu-id="65b7d-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span><span class="sxs-lookup"><span data-stu-id="65b7d-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span></span>|  
|[<span data-ttu-id="65b7d-113">\<code></span><span class="sxs-lookup"><span data-stu-id="65b7d-113">\<code></span></span>](../../../csharp/programming-guide/xmldoc/code.md)|<span data-ttu-id="65b7d-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span><span class="sxs-lookup"><span data-stu-id="65b7d-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span></span>|<span data-ttu-id="65b7d-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="65b7d-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span></span>|  
|[<span data-ttu-id="65b7d-116">\<example></span><span class="sxs-lookup"><span data-stu-id="65b7d-116">\<example></span></span>](../../../csharp/programming-guide/xmldoc/example.md)|[<span data-ttu-id="65b7d-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="65b7d-117">\<paramref></span></span>](../../../csharp/programming-guide/xmldoc/paramref.md)|[<span data-ttu-id="65b7d-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="65b7d-118">\<summary></span></span>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|<span data-ttu-id="65b7d-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="65b7d-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span></span>|<span data-ttu-id="65b7d-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="65b7d-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span></span>|<span data-ttu-id="65b7d-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="65b7d-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span></span>|  
|<span data-ttu-id="65b7d-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span><span class="sxs-lookup"><span data-stu-id="65b7d-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span></span>|[<span data-ttu-id="65b7d-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="65b7d-123">\<remarks></span></span>](../../../csharp/programming-guide/xmldoc/remarks.md)|[<span data-ttu-id="65b7d-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="65b7d-124">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[<span data-ttu-id="65b7d-125">\<list></span><span class="sxs-lookup"><span data-stu-id="65b7d-125">\<list></span></span>](../../../csharp/programming-guide/xmldoc/list.md)|[<span data-ttu-id="65b7d-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="65b7d-126">\<returns></span></span>](../../../csharp/programming-guide/xmldoc/returns.md)|[<span data-ttu-id="65b7d-127">\<value></span><span class="sxs-lookup"><span data-stu-id="65b7d-127">\<value></span></span>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 <span data-ttu-id="65b7d-128">(\* gibt an, dass der Compiler die Syntax überprüft.)</span><span class="sxs-lookup"><span data-stu-id="65b7d-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="65b7d-129">Wenn Sie möchten, dass im Text eines Dokumentationskommentars spitze Klammern erscheinen, verwenden Sie `<` und `>`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="65b7d-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`, as shown in the following example.</span></span>  
  
```xml  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## <a name="see-also"></a><span data-ttu-id="65b7d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65b7d-130">See Also</span></span>

- [<span data-ttu-id="65b7d-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="65b7d-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="65b7d-132">/doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="65b7d-132">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
- [<span data-ttu-id="65b7d-133">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="65b7d-133">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
