---
title: "Empfohlene Tags für Dokumentationskommentare (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4f4033ed66fd68afceb9d98cbc6da18c262ae02b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="160d2-102">Empfohlene Tags für Dokumentationskommentare (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="160d2-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="160d2-103">Der C#-Compiler verarbeitet Dokumentationskommentare in Ihrem Code und formatiert diese als XML in einer Datei, deren Namen Sie in der Befehlszeilenoption **/doc** angeben.</span><span class="sxs-lookup"><span data-stu-id="160d2-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="160d2-104">Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="160d2-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="160d2-105">Tags werden auf der Basis von Codekonstrukten wie Typen und Typmembern verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="160d2-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="160d2-106">Dokumentationskommentare können nicht auf einen Namespace angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="160d2-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="160d2-107">Der Compiler verarbeitet alle Tags, die gültige XML sind.</span><span class="sxs-lookup"><span data-stu-id="160d2-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="160d2-108">Die folgenden Tags stellen allgemein verwendete Funktionen in der Benutzerdokumentation bereit.</span><span class="sxs-lookup"><span data-stu-id="160d2-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="160d2-109">Tags</span><span class="sxs-lookup"><span data-stu-id="160d2-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="160d2-110">\<c></span><span class="sxs-lookup"><span data-stu-id="160d2-110">\<c></span></span>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[<span data-ttu-id="160d2-111">\<para></span><span class="sxs-lookup"><span data-stu-id="160d2-111">\<para></span></span>](../../../csharp/programming-guide/xmldoc/para.md)|<span data-ttu-id="160d2-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)*</span><span class="sxs-lookup"><span data-stu-id="160d2-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)*</span></span>|  
|[<span data-ttu-id="160d2-113">\<code></span><span class="sxs-lookup"><span data-stu-id="160d2-113">\<code></span></span>](../../../csharp/programming-guide/xmldoc/code.md)|<span data-ttu-id="160d2-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)*</span><span class="sxs-lookup"><span data-stu-id="160d2-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)*</span></span>|<span data-ttu-id="160d2-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)*</span><span class="sxs-lookup"><span data-stu-id="160d2-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)*</span></span>|  
|[<span data-ttu-id="160d2-116">\<example></span><span class="sxs-lookup"><span data-stu-id="160d2-116">\<example></span></span>](../../../csharp/programming-guide/xmldoc/example.md)|[<span data-ttu-id="160d2-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="160d2-117">\<paramref></span></span>](../../../csharp/programming-guide/xmldoc/paramref.md)|[<span data-ttu-id="160d2-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="160d2-118">\<summary></span></span>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|<span data-ttu-id="160d2-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)*</span><span class="sxs-lookup"><span data-stu-id="160d2-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)*</span></span>|<span data-ttu-id="160d2-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)*</span><span class="sxs-lookup"><span data-stu-id="160d2-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)*</span></span>|<span data-ttu-id="160d2-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)*</span><span class="sxs-lookup"><span data-stu-id="160d2-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)*</span></span>|  
|<span data-ttu-id="160d2-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)*</span><span class="sxs-lookup"><span data-stu-id="160d2-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)*</span></span>|[<span data-ttu-id="160d2-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="160d2-123">\<remarks></span></span>](../../../csharp/programming-guide/xmldoc/remarks.md)|[<span data-ttu-id="160d2-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="160d2-124">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[<span data-ttu-id="160d2-125">\<list></span><span class="sxs-lookup"><span data-stu-id="160d2-125">\<list></span></span>](../../../csharp/programming-guide/xmldoc/list.md)|[<span data-ttu-id="160d2-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="160d2-126">\<returns></span></span>](../../../csharp/programming-guide/xmldoc/returns.md)|[<span data-ttu-id="160d2-127">\<value></span><span class="sxs-lookup"><span data-stu-id="160d2-127">\<value></span></span>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 <span data-ttu-id="160d2-128">(* gibt an, dass der Compiler die Syntax überprüft.)</span><span class="sxs-lookup"><span data-stu-id="160d2-128">(* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="160d2-129">Wenn Sie möchten, dass im Text eines Dokumentationskommentars spitze Klammern erscheinen, verwenden Sie `<` und `>`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="160d2-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`, as shown in the following example.</span></span>  
  
```xml  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## <a name="see-also"></a><span data-ttu-id="160d2-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="160d2-130">See Also</span></span>  
 <span data-ttu-id="160d2-131">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="160d2-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="160d2-132">[/doc (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="160d2-132">[/doc (C# Compiler Options)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span></span>  
 [<span data-ttu-id="160d2-133">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="160d2-133">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

