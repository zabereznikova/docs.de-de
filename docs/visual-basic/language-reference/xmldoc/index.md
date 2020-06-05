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
ms.openlocfilehash: af57fc7d55c5cfda24a2fd9406b17dedee898760
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400098"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="a806a-102">Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a806a-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="a806a-103">Der Visual Basic-Compiler kann Dokumentations Kommentare in Ihrem Code in eine XML-Datei verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a806a-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="a806a-104">Sie können zusätzliche Tools verwenden, um die XML-Datei in die Dokumentation zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a806a-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="a806a-105">XML-Kommentare sind für Codekonstrukte zulässig, wie z. b. Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="a806a-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="a806a-106">Bei partiellen Typen kann nur ein Teil des Typs XML-Kommentare enthalten, obwohl es keine Einschränkung für die Kommentierung der Member gibt.</span><span class="sxs-lookup"><span data-stu-id="a806a-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a806a-107">Dokumentations Kommentare können nicht auf Namespaces angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a806a-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="a806a-108">Der Grund hierfür ist, dass ein Namespace mehrere Assemblys umfassen kann, und nicht alle Assemblys müssen gleichzeitig geladen werden.</span><span class="sxs-lookup"><span data-stu-id="a806a-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="a806a-109">Der Compiler verarbeitet alle Tags, die gültige XML-Daten sind.</span><span class="sxs-lookup"><span data-stu-id="a806a-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="a806a-110">Die folgenden Tags stellen häufig verwendete Funktionen in der Benutzerdokumentation bereit.</span><span class="sxs-lookup"><span data-stu-id="a806a-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[\<c>](c.md)|[\<code>](code.md)|[\<example>](example.md)|  
|<span data-ttu-id="a806a-111">[\<exception>](exception.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a806a-111">[\<exception>](exception.md) <sup>1</sup></span></span>|<span data-ttu-id="a806a-112">[\<include>](include.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a806a-112">[\<include>](include.md) <sup>1</sup></span></span>|[\<list>](list.md)|  
|[\<para>](para.md)|<span data-ttu-id="a806a-113">[\<param>](param.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a806a-113">[\<param>](param.md) <sup>1</sup></span></span>|[\<paramref>](paramref.md)|  
|<span data-ttu-id="a806a-114">[\<permission>](permission.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a806a-114">[\<permission>](permission.md) <sup>1</sup></span></span>|[\<remarks>](remarks.md)|[\<returns>](returns.md)|  
|<span data-ttu-id="a806a-115">[\<see>](see.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a806a-115">[\<see>](see.md) <sup>1</sup></span></span>|<span data-ttu-id="a806a-116">[\<seealso>](seealso.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a806a-116">[\<seealso>](seealso.md) <sup>1</sup></span></span>|[\<summary>](summary.md)|  
|<span data-ttu-id="a806a-117">[\<typeparam>](typeparam.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a806a-117">[\<typeparam>](typeparam.md) <sup>1</sup></span></span>|[\<value>](value.md)||  
  
 <span data-ttu-id="a806a-118">(<sup>1</sup> der Compiler überprüft die Syntax.)</span><span class="sxs-lookup"><span data-stu-id="a806a-118">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a806a-119">Wenn spitzen Klammern im Text eines Dokumentations Kommentars angezeigt werden sollen, verwenden Sie `&lt;` und `&gt;` .</span><span class="sxs-lookup"><span data-stu-id="a806a-119">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="a806a-120">Die Zeichenfolge wird z `"&lt;text in angle brackets&gt;"` . b. als angezeigt `<text in angle brackets>` .</span><span class="sxs-lookup"><span data-stu-id="a806a-120">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a806a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a806a-121">See also</span></span>

- [<span data-ttu-id="a806a-122">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="a806a-122">Documenting Your Code with XML</span></span>](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="a806a-123">-doc</span><span class="sxs-lookup"><span data-stu-id="a806a-123">-doc</span></span>](../../reference/command-line-compiler/doc.md)
- [<span data-ttu-id="a806a-124">Vorgehensweise: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="a806a-124">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
