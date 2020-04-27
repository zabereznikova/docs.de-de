---
title: Verwenden der XslCompiledTransform-Klasse
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: 6fc29b523e59590138cb7ca4db1b0da1bfee99c8
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937934"
---
# <a name="using-the-xslcompiledtransform-class"></a><span data-ttu-id="1dd0c-102">Verwenden der XslCompiledTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="1dd0c-102">Using the XslCompiledTransform Class</span></span>
<span data-ttu-id="1dd0c-103">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ist der XSLT-Prozessor in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1dd0c-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the Microsoft .NET Framework XSLT processor.</span></span> <span data-ttu-id="1dd0c-104">Diese Klasse wird zum Kompilieren von Stylesheets und zum Ausführen von XSLT-Transformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1dd0c-104">This class is used to compile style sheets and execute XSLT transformations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1dd0c-105">Obwohl die Gesamtleistung der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse besser ist als die der <xref:System.Xml.Xsl.XslTransform>-Klasse, ist die Leistung der <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse möglicherweise langsamer als die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode der <xref:System.Xml.Xsl.XslTransform>-Klasse, wenn sie zum ersten Mal für eine Transformation aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1dd0c-105">Although the overall performance of the <xref:System.Xml.Xsl.XslCompiledTransform> class is better than the <xref:System.Xml.Xsl.XslTransform> class, the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslCompiledTransform> class might perform more slowly than the <xref:System.Xml.Xsl.XslTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslTransform> class the first time it is called on a transformation.</span></span> <span data-ttu-id="1dd0c-106">Dies liegt daran, dass die XSLT-Datei zunächst kompiliert werden muss, bevor sie geladen wird.</span><span class="sxs-lookup"><span data-stu-id="1dd0c-106">This is because the XSLT file must be compiled before it is loaded.</span></span> <span data-ttu-id="1dd0c-107">Weitere Informationen finden Sie im folgenden Blogbeitrag: [XslCompiledTransform Slower than XslTransform? (Ist XslCompiledTransform langsamer als XslTransform?)](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span><span class="sxs-lookup"><span data-stu-id="1dd0c-107">For more information, see the following blog post: [XslCompiledTransform Slower than XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1dd0c-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1dd0c-108">In This Section</span></span>  
 [<span data-ttu-id="1dd0c-109">Eingaben für die XslCompiledTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="1dd0c-109">Inputs to the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="1dd0c-110">Beschreibt die verfügbaren XSLT-Eingabeoptionen.</span><span class="sxs-lookup"><span data-stu-id="1dd0c-110">Describes the available XSLT input options.</span></span>  
  
 [<span data-ttu-id="1dd0c-111">Ausgabeoptionen für die XslCompiledTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="1dd0c-111">Output Options on the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="1dd0c-112">Beschreibt die verfügbaren XSLT-Ausgabeoptionen.</span><span class="sxs-lookup"><span data-stu-id="1dd0c-112">Describes the available XSLT output options.</span></span>  
  
 [<span data-ttu-id="1dd0c-113">Auflösen von externen Ressourcen während der XSLT-Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="1dd0c-113">Resolving External Resources During XSLT Processing</span></span>](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 <span data-ttu-id="1dd0c-114">Erläutert die Verwendung der <xref:System.Xml.XmlResolver>-Klasse beim Auflösen externer Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="1dd0c-114">Discusses using the <xref:System.Xml.XmlResolver> class to resolve external resources.</span></span>  
  
 [<span data-ttu-id="1dd0c-115">Erweitern von XSLT-Stylesheets</span><span class="sxs-lookup"><span data-stu-id="1dd0c-115">Extending XSLT Style Sheets</span></span>](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 <span data-ttu-id="1dd0c-116">Erläutert die Unterstützung von XSLT-Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="1dd0c-116">Discusses how XSLT extensions are supported.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="1dd0c-117">Wiederherstellbare XSLT-Fehler</span><span class="sxs-lookup"><span data-stu-id="1dd0c-117">Recoverable XSLT Errors</span></span>](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|<span data-ttu-id="1dd0c-118">Listet die freigegebenen Verhaltensweisen auf, die gemäß der W3C-Empfehlung zu XSL-Transformationen (XSLT), Version 1.0, zugelassen sind, und beschreibt, wie diese Verhaltensweisen von der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="1dd0c-118">Lists discretionary behaviors allowed by the World Wide Web Consortium (W3C) XSLT 1.0 recommendation and describes how these behaviors are handled by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>|  
|[<span data-ttu-id="1dd0c-119">How to: Transformieren eines Knotenfragments</span><span class="sxs-lookup"><span data-stu-id="1dd0c-119">How to: Transform a Node Fragment</span></span>](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|<span data-ttu-id="1dd0c-120">Beschreibt, wie ein Knotenfragment transformiert wird.</span><span class="sxs-lookup"><span data-stu-id="1dd0c-120">Describes how to transform a node fragment.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="1dd0c-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1dd0c-121">Related Sections</span></span>  
 [<span data-ttu-id="1dd0c-122">Migrieren von der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="1dd0c-122">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="1dd0c-123">Erläutert die Migration von Code von der <xref:System.Xml.Xsl.XslTransform>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1dd0c-123">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dd0c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1dd0c-124">See also</span></span>

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
