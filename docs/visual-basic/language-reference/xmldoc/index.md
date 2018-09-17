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
ms.openlocfilehash: 3b2dec4224006d35fb9add11e170b9dcbeeafcf3
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2018
ms.locfileid: "45649964"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="1b2ba-102">Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b2ba-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="1b2ba-103">Visual Basic-Compiler kann Dokumentationskommentaren in Ihrem Code in eine XML-Datei verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="1b2ba-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="1b2ba-104">Sie können zusätzliche Tools verwenden, zum Verarbeiten der XML-Datei in der Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="1b2ba-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="1b2ba-105">XML-Kommentare dürfen in Codekonstrukten wie Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="1b2ba-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="1b2ba-106">Für partielle Typen haben nur ein Teil des Typs XML-Kommentaren, aber es keine Einschränkung gibt für die Kommentierung von Membern.</span><span class="sxs-lookup"><span data-stu-id="1b2ba-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b2ba-107">Dokumentationskommentare können nicht auf Namespaces angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b2ba-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="1b2ba-108">Der Grund ist, dass ein Namespace mehrere Assemblys umfassen kann und nicht alle Assemblys gleichzeitig geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1b2ba-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="1b2ba-109">Der Compiler verarbeitet alle Tags, die gültigen XML-Code ist.</span><span class="sxs-lookup"><span data-stu-id="1b2ba-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="1b2ba-110">Die folgenden Tags stellen häufig verwendete Funktionen in der Dokumentation für die Benutzer bereit.</span><span class="sxs-lookup"><span data-stu-id="1b2ba-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="1b2ba-111">\<c></span><span class="sxs-lookup"><span data-stu-id="1b2ba-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="1b2ba-112">\<code></span><span class="sxs-lookup"><span data-stu-id="1b2ba-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="1b2ba-113">\<example></span><span class="sxs-lookup"><span data-stu-id="1b2ba-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="1b2ba-114">[\<Ausnahme >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1b2ba-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="1b2ba-115">[\<umfassen >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1b2ba-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="1b2ba-116">\<list></span><span class="sxs-lookup"><span data-stu-id="1b2ba-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="1b2ba-117">\<para></span><span class="sxs-lookup"><span data-stu-id="1b2ba-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="1b2ba-118">[\<Param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1b2ba-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="1b2ba-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="1b2ba-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="1b2ba-120">[\<Berechtigung >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1b2ba-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="1b2ba-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="1b2ba-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="1b2ba-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="1b2ba-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="1b2ba-123">[\<finden Sie unter >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1b2ba-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="1b2ba-124">[\<Seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1b2ba-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="1b2ba-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="1b2ba-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="1b2ba-126">[\<Typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1b2ba-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="1b2ba-127">\<value></span><span class="sxs-lookup"><span data-stu-id="1b2ba-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="1b2ba-128">(<sup>1</sup> der Compiler überprüft die Syntax.)</span><span class="sxs-lookup"><span data-stu-id="1b2ba-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b2ba-129">Wenn die Spitze Klammern im Text eines Dokumentationskommentars angezeigt werden soll, verwenden Sie `&lt;` und `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="1b2ba-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="1b2ba-130">Z. B. die Zeichenfolge `"&lt;text in angle brackets&gt;"` hostnamensadresse `<text in angle brackets>`.</span><span class="sxs-lookup"><span data-stu-id="1b2ba-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b2ba-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b2ba-131">See Also</span></span>  
 [<span data-ttu-id="1b2ba-132">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="1b2ba-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="1b2ba-133">/doc</span><span class="sxs-lookup"><span data-stu-id="1b2ba-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="1b2ba-134">Gewusst wie: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="1b2ba-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
