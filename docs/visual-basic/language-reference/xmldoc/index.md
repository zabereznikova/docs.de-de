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
ms.openlocfilehash: 2d6519af8ca1a0e2d59131eec4d63646dce7318b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913502"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="01dcb-102">Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01dcb-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="01dcb-103">Der Visual Basic-Compiler kann Dokumentations Kommentare in Ihrem Code in eine XML-Datei verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="01dcb-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="01dcb-104">Sie können zusätzliche Tools verwenden, um die XML-Datei in die Dokumentation zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="01dcb-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="01dcb-105">XML-Kommentare sind für Codekonstrukte zulässig, wie z. b. Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="01dcb-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="01dcb-106">Bei partiellen Typen kann nur ein Teil des Typs XML-Kommentare enthalten, obwohl es keine Einschränkung für die Kommentierung der Member gibt.</span><span class="sxs-lookup"><span data-stu-id="01dcb-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01dcb-107">Dokumentations Kommentare können nicht auf Namespaces angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="01dcb-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="01dcb-108">Der Grund hierfür ist, dass ein Namespace mehrere Assemblys umfassen kann, und nicht alle Assemblys müssen gleichzeitig geladen werden.</span><span class="sxs-lookup"><span data-stu-id="01dcb-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="01dcb-109">Der Compiler verarbeitet alle Tags, die gültige XML-Daten sind.</span><span class="sxs-lookup"><span data-stu-id="01dcb-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="01dcb-110">Die folgenden Tags stellen häufig verwendete Funktionen in der Benutzerdokumentation bereit.</span><span class="sxs-lookup"><span data-stu-id="01dcb-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="01dcb-111">\<c></span><span class="sxs-lookup"><span data-stu-id="01dcb-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="01dcb-112">\<code></span><span class="sxs-lookup"><span data-stu-id="01dcb-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="01dcb-113">\<example></span><span class="sxs-lookup"><span data-stu-id="01dcb-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="01dcb-114">Ausnahme > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/exception.md)</span><span class="sxs-lookup"><span data-stu-id="01dcb-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="01dcb-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="01dcb-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="01dcb-116">\<list></span><span class="sxs-lookup"><span data-stu-id="01dcb-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="01dcb-117">\<para></span><span class="sxs-lookup"><span data-stu-id="01dcb-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="01dcb-118">param > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/param.md)</span><span class="sxs-lookup"><span data-stu-id="01dcb-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="01dcb-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="01dcb-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="01dcb-120">Berechtigung > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/permission.md)</span><span class="sxs-lookup"><span data-stu-id="01dcb-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="01dcb-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="01dcb-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="01dcb-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="01dcb-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="01dcb-123">siehe > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/see.md)</span><span class="sxs-lookup"><span data-stu-id="01dcb-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="01dcb-124">seeauch > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/seealso.md)</span><span class="sxs-lookup"><span data-stu-id="01dcb-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="01dcb-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="01dcb-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="01dcb-126">typeparam-> <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/typeparam.md)</span><span class="sxs-lookup"><span data-stu-id="01dcb-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="01dcb-127">\<value></span><span class="sxs-lookup"><span data-stu-id="01dcb-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="01dcb-128">(<sup>1</sup> der Compiler überprüft die Syntax.)</span><span class="sxs-lookup"><span data-stu-id="01dcb-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01dcb-129">Wenn spitzen Klammern im Text eines Dokumentations Kommentars angezeigt werden sollen, verwenden `&lt;` Sie und. `&gt;`</span><span class="sxs-lookup"><span data-stu-id="01dcb-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="01dcb-130">Die Zeichenfolge `"&lt;text in angle brackets&gt;"` wird z. b. `<text in angle brackets>`als angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01dcb-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01dcb-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01dcb-131">See also</span></span>

- [<span data-ttu-id="01dcb-132">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="01dcb-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="01dcb-133">/doc</span><span class="sxs-lookup"><span data-stu-id="01dcb-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="01dcb-134">Vorgehensweise: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="01dcb-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
