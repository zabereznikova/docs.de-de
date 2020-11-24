---
title: Verwenden der XslCompiledTransform-Klasse
ms.date: 03/30/2017
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: f2eae6f10cc2adf4628a0c2626617ef9a027c598
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821761"
---
# <a name="using-the-xslcompiledtransform-class"></a><span data-ttu-id="df407-102">Verwenden der XslCompiledTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="df407-102">Using the XslCompiledTransform Class</span></span>
<span data-ttu-id="df407-103">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ist der XSLT-Prozessor in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="df407-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the Microsoft .NET Framework XSLT processor.</span></span> <span data-ttu-id="df407-104">Diese Klasse wird zum Kompilieren von Stylesheets und zum Ausführen von XSLT-Transformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="df407-104">This class is used to compile style sheets and execute XSLT transformations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df407-105">Obwohl die Gesamtleistung der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse besser ist als die der <xref:System.Xml.Xsl.XslTransform>-Klasse, ist die Leistung der <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse möglicherweise langsamer als die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode der <xref:System.Xml.Xsl.XslTransform>-Klasse, wenn sie zum ersten Mal für eine Transformation aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="df407-105">Although the overall performance of the <xref:System.Xml.Xsl.XslCompiledTransform> class is better than the <xref:System.Xml.Xsl.XslTransform> class, the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslCompiledTransform> class might perform more slowly than the <xref:System.Xml.Xsl.XslTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslTransform> class the first time it is called on a transformation.</span></span> <span data-ttu-id="df407-106">Dies liegt daran, dass die XSLT-Datei zunächst kompiliert werden muss, bevor sie geladen wird.</span><span class="sxs-lookup"><span data-stu-id="df407-106">This is because the XSLT file must be compiled before it is loaded.</span></span> <span data-ttu-id="df407-107">Weitere Informationen finden Sie im folgenden Blogbeitrag: [XslCompiledTransform Slower than XslTransform? (Ist XslCompiledTransform langsamer als XslTransform?)](/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span><span class="sxs-lookup"><span data-stu-id="df407-107">For more information, see the following blog post: [XslCompiledTransform Slower than XslTransform?](/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="df407-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="df407-108">In This Section</span></span>  
 [<span data-ttu-id="df407-109">Eingaben für die XslCompiledTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="df407-109">Inputs to the XslCompiledTransform Class</span></span>](inputs-to-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="df407-110">Beschreibt die verfügbaren XSLT-Eingabeoptionen.</span><span class="sxs-lookup"><span data-stu-id="df407-110">Describes the available XSLT input options.</span></span>  
  
 [<span data-ttu-id="df407-111">Ausgabeoptionen für die XslCompiledTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="df407-111">Output Options on the XslCompiledTransform Class</span></span>](output-options-on-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="df407-112">Beschreibt die verfügbaren XSLT-Ausgabeoptionen.</span><span class="sxs-lookup"><span data-stu-id="df407-112">Describes the available XSLT output options.</span></span>  
  
 [<span data-ttu-id="df407-113">Auflösen von externen Ressourcen während der XSLT-Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="df407-113">Resolving External Resources During XSLT Processing</span></span>](resolving-external-resources-during-xslt-processing.md)  
 <span data-ttu-id="df407-114">Erläutert die Verwendung der <xref:System.Xml.XmlResolver>-Klasse beim Auflösen externer Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="df407-114">Discusses using the <xref:System.Xml.XmlResolver> class to resolve external resources.</span></span>  
  
 [<span data-ttu-id="df407-115">Erweitern von XSLT-Stylesheets</span><span class="sxs-lookup"><span data-stu-id="df407-115">Extending XSLT Style Sheets</span></span>](extending-xslt-style-sheets.md)  
 <span data-ttu-id="df407-116">Erläutert die Unterstützung von XSLT-Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="df407-116">Discusses how XSLT extensions are supported.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="df407-117">Wiederherstellbare XSLT-Fehler</span><span class="sxs-lookup"><span data-stu-id="df407-117">Recoverable XSLT Errors</span></span>](recoverable-xslt-errors.md)|<span data-ttu-id="df407-118">Listet die freigegebenen Verhaltensweisen auf, die gemäß der W3C-Empfehlung zu XSL-Transformationen (XSLT), Version 1.0, zugelassen sind, und beschreibt, wie diese Verhaltensweisen von der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="df407-118">Lists discretionary behaviors allowed by the World Wide Web Consortium (W3C) XSLT 1.0 recommendation and describes how these behaviors are handled by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>|  
|[<span data-ttu-id="df407-119">How to: Transformieren eines Knotenfragments</span><span class="sxs-lookup"><span data-stu-id="df407-119">How to: Transform a Node Fragment</span></span>](how-to-transform-a-node-fragment.md)|<span data-ttu-id="df407-120">Beschreibt, wie ein Knotenfragment transformiert wird.</span><span class="sxs-lookup"><span data-stu-id="df407-120">Describes how to transform a node fragment.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="df407-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="df407-121">Related Sections</span></span>  
 [<span data-ttu-id="df407-122">Migrieren von der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="df407-122">Migrating From the XslTransform Class</span></span>](migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="df407-123">Erläutert die Migration von Code von der <xref:System.Xml.Xsl.XslTransform>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="df407-123">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df407-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df407-124">See also</span></span>

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
