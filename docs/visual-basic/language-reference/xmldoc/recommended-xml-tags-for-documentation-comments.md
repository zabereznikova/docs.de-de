---
title: "Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
dev_langs:
- VB
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e4a6c3128a69e8d666d44882ef3eac9f9a31a51a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="290a0-102">Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="290a0-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="290a0-103">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler Dokumentationskommentare im Code, um eine XML-Datei verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="290a0-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="290a0-104">Zusätzliche Tools können Sie um die XML-Datei in der Dokumentation zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="290a0-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="290a0-105">XML-Kommentare dürfen für Codekonstrukte wie Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="290a0-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="290a0-106">Für partielle Typen kann nur ein Teil des Typs XML-Kommentare haben, obwohl es keine Einschränkung besteht hinsichtlich seiner Member kommentieren.</span><span class="sxs-lookup"><span data-stu-id="290a0-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="290a0-107">Dokumentationskommentare können nicht auf Namespaces angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="290a0-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="290a0-108">Der Grund ist, dass ein Namespace kann mehrere Assemblys umfassen, und nicht alle Assemblys gleichzeitig geladen werden.</span><span class="sxs-lookup"><span data-stu-id="290a0-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="290a0-109">Der Compiler verarbeitet jedes Tag, das gültiges XML darstellt.</span><span class="sxs-lookup"><span data-stu-id="290a0-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="290a0-110">Die folgenden Tags bieten häufig verwendete Funktionen in der Dokumentation für die Benutzer.</span><span class="sxs-lookup"><span data-stu-id="290a0-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="290a0-111">\<c ></span><span class="sxs-lookup"><span data-stu-id="290a0-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="290a0-112">\<Code ></span><span class="sxs-lookup"><span data-stu-id="290a0-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="290a0-113">\<Beispiel ></span><span class="sxs-lookup"><span data-stu-id="290a0-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="290a0-114">[\<Ausnahme >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="290a0-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="290a0-115">[\<umfassen >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="290a0-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="290a0-116">\<list></span><span class="sxs-lookup"><span data-stu-id="290a0-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="290a0-117">\<Para ></span><span class="sxs-lookup"><span data-stu-id="290a0-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="290a0-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="290a0-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="290a0-119">\<Paramref ></span><span class="sxs-lookup"><span data-stu-id="290a0-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="290a0-120">[\<Berechtigung >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="290a0-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="290a0-121">\<Hinweise ></span><span class="sxs-lookup"><span data-stu-id="290a0-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="290a0-122">\<Gibt ></span><span class="sxs-lookup"><span data-stu-id="290a0-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="290a0-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="290a0-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="290a0-124">[\<Seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="290a0-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="290a0-125">\<Zusammenfassung ></span><span class="sxs-lookup"><span data-stu-id="290a0-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="290a0-126">[\<Typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="290a0-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="290a0-127">\<Wert ></span><span class="sxs-lookup"><span data-stu-id="290a0-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="290a0-128">(<sup>1</sup> der Compiler überprüft Syntax.)</span><span class="sxs-lookup"><span data-stu-id="290a0-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="290a0-129">Wenn spitze Klammern im Text eines angezeigt werden soll, verwenden Sie `<` und `>`.</span><span class="sxs-lookup"><span data-stu-id="290a0-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`.</span></span> <span data-ttu-id="290a0-130">Z. B. die Zeichenfolge `"<text in angle brackets>"` erscheint als `<text in angle``brackets>`.</span><span class="sxs-lookup"><span data-stu-id="290a0-130">For example, the string `"<text in angle brackets>"` will appear as `<text in angle``brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290a0-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="290a0-131">See Also</span></span>  
 <span data-ttu-id="290a0-132">[Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="290a0-132">[Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
<span data-ttu-id="290a0-133"> [/ doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span><span class="sxs-lookup"><span data-stu-id="290a0-133"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span></span>  
<span data-ttu-id="290a0-134"> [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="290a0-134"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span></span>
