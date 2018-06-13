---
title: Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 8f27a892117980e89fa7143b7e49551b9e8703f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604420"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="609d3-102">Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="609d3-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="609d3-103">Visual Basic-Compiler kann Dokumentationskommentare in Ihrem Code in eine XML-Datei verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="609d3-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="609d3-104">Sie können zusätzliche Tools verwenden, zum Verarbeiten der XML-Datei in der Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="609d3-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="609d3-105">XML-Kommentare dürfen auf Codekonstrukte wie Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="609d3-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="609d3-106">Für partielle Typen kann nur ein Teil des Typs XML-Kommentare, haben, obwohl es keine Einschränkung gibt für die Kommentierung von Membern.</span><span class="sxs-lookup"><span data-stu-id="609d3-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="609d3-107">Dokumentationskommentare können nicht auf Namespaces angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="609d3-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="609d3-108">Der Grund ist, dass ein Namespace mehrere Assemblys umfassen kann und nicht alle Assemblys gleichzeitig geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="609d3-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="609d3-109">Der Compiler verarbeitet alle Tags, die XML-Daten gültig sind.</span><span class="sxs-lookup"><span data-stu-id="609d3-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="609d3-110">Die folgenden Tags stellen häufig verwendete Funktionen in der Dokumentation für die Benutzer bereit.</span><span class="sxs-lookup"><span data-stu-id="609d3-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="609d3-111">\<c></span><span class="sxs-lookup"><span data-stu-id="609d3-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="609d3-112">\<code></span><span class="sxs-lookup"><span data-stu-id="609d3-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="609d3-113">\<example></span><span class="sxs-lookup"><span data-stu-id="609d3-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="609d3-114">[\<Ausnahme >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="609d3-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="609d3-115">[\<umfassen >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="609d3-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="609d3-116">\<list></span><span class="sxs-lookup"><span data-stu-id="609d3-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="609d3-117">\<para></span><span class="sxs-lookup"><span data-stu-id="609d3-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="609d3-118">[\<Param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="609d3-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="609d3-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="609d3-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="609d3-120">[\<Berechtigung >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="609d3-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="609d3-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="609d3-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="609d3-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="609d3-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="609d3-123">[\<finden Sie unter >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="609d3-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="609d3-124">[\<Seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="609d3-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="609d3-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="609d3-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="609d3-126">[\<Typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="609d3-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="609d3-127">\<value></span><span class="sxs-lookup"><span data-stu-id="609d3-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="609d3-128">(<sup>1</sup> der Compiler überprüft die Syntax.)</span><span class="sxs-lookup"><span data-stu-id="609d3-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="609d3-129">Wenn Sie spitze Klammern, um im Text des kein Dokumentationskommentar angezeigt werden soll, verwenden `<` und `>`.</span><span class="sxs-lookup"><span data-stu-id="609d3-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`.</span></span> <span data-ttu-id="609d3-130">Z. B. die Zeichenfolge `"<text in angle brackets>"` hostnamensadresse `<text in angle``brackets>`.</span><span class="sxs-lookup"><span data-stu-id="609d3-130">For example, the string `"<text in angle brackets>"` will appear as `<text in angle``brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="609d3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="609d3-131">See Also</span></span>  
 [<span data-ttu-id="609d3-132">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="609d3-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="609d3-133">/doc</span><span class="sxs-lookup"><span data-stu-id="609d3-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="609d3-134">Gewusst wie: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="609d3-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
