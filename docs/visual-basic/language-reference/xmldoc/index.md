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
ms.openlocfilehash: 7830db136e9b900458496b36df5bc37f76661129
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523965"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="f3691-102">Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3691-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="f3691-103">Der Visual Basic-Compiler kann Dokumentations Kommentare in Ihrem Code in eine XML-Datei verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f3691-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="f3691-104">Sie können zusätzliche Tools verwenden, um die XML-Datei in die Dokumentation zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f3691-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="f3691-105">XML-Kommentare sind für Codekonstrukte zulässig, wie z. b. Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="f3691-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="f3691-106">Bei partiellen Typen kann nur ein Teil des Typs XML-Kommentare enthalten, obwohl es keine Einschränkung für die Kommentierung der Member gibt.</span><span class="sxs-lookup"><span data-stu-id="f3691-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3691-107">Dokumentations Kommentare können nicht auf Namespaces angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="f3691-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="f3691-108">Der Grund hierfür ist, dass ein Namespace mehrere Assemblys umfassen kann, und nicht alle Assemblys müssen gleichzeitig geladen werden.</span><span class="sxs-lookup"><span data-stu-id="f3691-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="f3691-109">Der Compiler verarbeitet alle Tags, die gültige XML-Daten sind.</span><span class="sxs-lookup"><span data-stu-id="f3691-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="f3691-110">Die folgenden Tags stellen häufig verwendete Funktionen in der Benutzerdokumentation bereit.</span><span class="sxs-lookup"><span data-stu-id="f3691-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="f3691-111">\<c></span><span class="sxs-lookup"><span data-stu-id="f3691-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="f3691-112">\<code></span><span class="sxs-lookup"><span data-stu-id="f3691-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="f3691-113">\<example></span><span class="sxs-lookup"><span data-stu-id="f3691-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="f3691-114">[\<exception >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f3691-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="f3691-115">[\<include >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f3691-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="f3691-116">\<list></span><span class="sxs-lookup"><span data-stu-id="f3691-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="f3691-117">\<para></span><span class="sxs-lookup"><span data-stu-id="f3691-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="f3691-118">[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f3691-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="f3691-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="f3691-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="f3691-120">[\<permission >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f3691-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="f3691-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="f3691-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="f3691-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="f3691-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="f3691-123">[\<see >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f3691-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="f3691-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f3691-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="f3691-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="f3691-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="f3691-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f3691-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="f3691-127">\<value></span><span class="sxs-lookup"><span data-stu-id="f3691-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="f3691-128">(<sup>1</sup> der Compiler überprüft die Syntax.)</span><span class="sxs-lookup"><span data-stu-id="f3691-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3691-129">Wenn Sie möchten, dass im Text eines Dokumentations Kommentars spitzen Klammern angezeigt werden, verwenden Sie `&lt;` und `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="f3691-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="f3691-130">Beispielsweise wird die Zeichenfolge `"&lt;text in angle brackets&gt;"` als `<text in angle brackets>` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3691-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3691-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3691-131">See also</span></span>

- [<span data-ttu-id="f3691-132">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="f3691-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="f3691-133">-doc</span><span class="sxs-lookup"><span data-stu-id="f3691-133">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="f3691-134">Gewusst wie: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="f3691-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
