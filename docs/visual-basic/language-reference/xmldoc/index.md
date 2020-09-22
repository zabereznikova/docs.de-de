---
title: Empfohlene XML-Tags für Dokumentations Kommentare
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 9f877ee3fc9d616dc1e946293489a8aab96ac2e1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872793"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="93dd3-102">Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93dd3-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>

<span data-ttu-id="93dd3-103">Der Visual Basic-Compiler kann Dokumentations Kommentare in Ihrem Code in eine XML-Datei verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="93dd3-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="93dd3-104">Sie können zusätzliche Tools verwenden, um die XML-Datei in die Dokumentation zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="93dd3-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="93dd3-105">XML-Kommentare sind für Codekonstrukte zulässig, wie z. b. Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="93dd3-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="93dd3-106">Bei partiellen Typen kann nur ein Teil des Typs XML-Kommentare enthalten, obwohl es keine Einschränkung für die Kommentierung der Member gibt.</span><span class="sxs-lookup"><span data-stu-id="93dd3-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93dd3-107">Dokumentations Kommentare können nicht auf Namespaces angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="93dd3-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="93dd3-108">Der Grund hierfür ist, dass ein Namespace mehrere Assemblys umfassen kann, und nicht alle Assemblys müssen gleichzeitig geladen werden.</span><span class="sxs-lookup"><span data-stu-id="93dd3-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="93dd3-109">Der Compiler verarbeitet alle Tags, die gültige XML-Daten sind.</span><span class="sxs-lookup"><span data-stu-id="93dd3-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="93dd3-110">Die folgenden Tags stellen häufig verwendete Funktionen in der Benutzerdokumentation bereit.</span><span class="sxs-lookup"><span data-stu-id="93dd3-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[\<c>](c.md)|[\<code>](code.md)|[\<example>](example.md)|  
|<span data-ttu-id="93dd3-111">[\<exception>](exception.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="93dd3-111">[\<exception>](exception.md) <sup>1</sup></span></span>|<span data-ttu-id="93dd3-112">[\<include>](include.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="93dd3-112">[\<include>](include.md) <sup>1</sup></span></span>|[\<list>](list.md)|  
|[\<para>](para.md)|<span data-ttu-id="93dd3-113">[\<param>](param.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="93dd3-113">[\<param>](param.md) <sup>1</sup></span></span>|[\<paramref>](paramref.md)|  
|<span data-ttu-id="93dd3-114">[\<permission>](permission.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="93dd3-114">[\<permission>](permission.md) <sup>1</sup></span></span>|[\<remarks>](remarks.md)|[\<returns>](returns.md)|  
|<span data-ttu-id="93dd3-115">[\<see>](see.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="93dd3-115">[\<see>](see.md) <sup>1</sup></span></span>|<span data-ttu-id="93dd3-116">[\<seealso>](seealso.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="93dd3-116">[\<seealso>](seealso.md) <sup>1</sup></span></span>|[\<summary>](summary.md)|  
|<span data-ttu-id="93dd3-117">[\<typeparam>](typeparam.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="93dd3-117">[\<typeparam>](typeparam.md) <sup>1</sup></span></span>|[\<value>](value.md)||  
  
 <span data-ttu-id="93dd3-118">(<sup>1</sup> der Compiler überprüft die Syntax.)</span><span class="sxs-lookup"><span data-stu-id="93dd3-118">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93dd3-119">Wenn spitzen Klammern im Text eines Dokumentations Kommentars angezeigt werden sollen, verwenden Sie `&lt;` und `&gt;` .</span><span class="sxs-lookup"><span data-stu-id="93dd3-119">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="93dd3-120">Die Zeichenfolge wird z `"&lt;text in angle brackets&gt;"` . b. als angezeigt `<text in angle brackets>` .</span><span class="sxs-lookup"><span data-stu-id="93dd3-120">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93dd3-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93dd3-121">See also</span></span>

- [<span data-ttu-id="93dd3-122">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="93dd3-122">Documenting Your Code with XML</span></span>](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="93dd3-123">-doc</span><span class="sxs-lookup"><span data-stu-id="93dd3-123">-doc</span></span>](../../reference/command-line-compiler/doc.md)
- [<span data-ttu-id="93dd3-124">Vorgehensweise: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="93dd3-124">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
