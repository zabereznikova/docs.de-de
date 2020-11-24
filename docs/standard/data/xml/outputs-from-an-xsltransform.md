---
title: Ausgaben aus "XslTransform"
ms.date: 03/30/2017
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
ms.openlocfilehash: 765f6f9a91cc44a55ab0d66ed71f19f60ef81a56
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830063"
---
# <a name="outputs-from-an-xsltransform"></a><span data-ttu-id="d4eec-102">Ausgaben aus "XslTransform"</span><span class="sxs-lookup"><span data-stu-id="d4eec-102">Outputs from an XslTransform</span></span>
<span data-ttu-id="d4eec-103">Stylesheets bestimmen das Ausgabeformat mithilfe einer `<xsl:output>`-Anweisung mit dem `method`-Attribut. In der folgenden Tabelle wird das Ausgabeformat bei Verwendung der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode für das Schreiben der Ausgabe beschrieben; außerdem wird das Ausgabeformat als <xref:System.IO.Stream> oder <xref:System.IO.TextWriter> deklariert.</span><span class="sxs-lookup"><span data-stu-id="d4eec-103">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4eec-104">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="d4eec-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="d4eec-105">Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen.</span><span class="sxs-lookup"><span data-stu-id="d4eec-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="d4eec-106">Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="d4eec-106">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="d4eec-107">Stylesheets bestimmen das Ausgabeformat mithilfe einer `<xsl:output>`-Anweisung mit dem `method`-Attribut. In der folgenden Tabelle wird das Ausgabeformat bei Verwendung der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode für das Schreiben der Ausgabe beschrieben; außerdem wird das Ausgabeformat als <xref:System.IO.Stream> oder <xref:System.IO.TextWriter> deklariert.</span><span class="sxs-lookup"><span data-stu-id="d4eec-107">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="d4eec-108">In der folgenden Tabelle wird beschrieben, was geschieht, wenn von der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode ein Ausgabetyp in Verbindung mit einer `<xsl:output>`-Anweisung deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="d4eec-108">The following table describes what happens when an output type is declared by the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method in conjunction with the use of an `<xsl:output>` statement:</span></span>  
  
|<span data-ttu-id="d4eec-109">\<xsl:output method = >-Attribut</span><span class="sxs-lookup"><span data-stu-id="d4eec-109">\<xsl:output method = > attribute</span></span>|<span data-ttu-id="d4eec-110">Ergebnisformat</span><span class="sxs-lookup"><span data-stu-id="d4eec-110">Result format</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="d4eec-111">method="xml"</span><span class="sxs-lookup"><span data-stu-id="d4eec-111">method="xml"</span></span>|<span data-ttu-id="d4eec-112">XML</span><span class="sxs-lookup"><span data-stu-id="d4eec-112">XML</span></span>|  
|<span data-ttu-id="d4eec-113">method="html"</span><span class="sxs-lookup"><span data-stu-id="d4eec-113">method="html"</span></span>|<span data-ttu-id="d4eec-114">HTML</span><span class="sxs-lookup"><span data-stu-id="d4eec-114">HTML</span></span>|  
|<span data-ttu-id="d4eec-115">method="text"</span><span class="sxs-lookup"><span data-stu-id="d4eec-115">method="text"</span></span>|<span data-ttu-id="d4eec-116">Text</span><span class="sxs-lookup"><span data-stu-id="d4eec-116">Text</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d4eec-117">Hinweis: Wenn die Ausgabe der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode ein <xref:System.Xml.XmlReader> oder ein <xref:System.Xml.XmlWriter> ist, wird die `<xsl:output>`-Anweisung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d4eec-117">Note: The `<xsl:output>` statement is ignored when the output of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="d4eec-118">Wenn die Ausgabe der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode ein <xref:System.IO.Stream> oder ein <xref:System.IO.TextWriter> ist, werden die folgenden Attribute unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d4eec-118">The following attributes are supported when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>:</span></span>  
  
- <span data-ttu-id="d4eec-119">encoding\*</span><span class="sxs-lookup"><span data-stu-id="d4eec-119">encoding\*</span></span>  
  
- <span data-ttu-id="d4eec-120">omit-xml-declaration</span><span class="sxs-lookup"><span data-stu-id="d4eec-120">omit-xml-declaration</span></span>  
  
- <span data-ttu-id="d4eec-121">Eigenständig</span><span class="sxs-lookup"><span data-stu-id="d4eec-121">standalone</span></span>  
  
- <span data-ttu-id="d4eec-122">doctype-public</span><span class="sxs-lookup"><span data-stu-id="d4eec-122">doctype-public</span></span>  
  
- <span data-ttu-id="d4eec-123">doctype-system</span><span class="sxs-lookup"><span data-stu-id="d4eec-123">doctype-system</span></span>  
  
- <span data-ttu-id="d4eec-124">cdata-section-elements</span><span class="sxs-lookup"><span data-stu-id="d4eec-124">cdata-section-elements</span></span>  
  
- <span data-ttu-id="d4eec-125">indent</span><span class="sxs-lookup"><span data-stu-id="d4eec-125">indent</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d4eec-126">\*Das encoding-Attribut wird ignoriert, wenn die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode die Ausgabe an <xref:System.IO.TextWriter> sendet.</span><span class="sxs-lookup"><span data-stu-id="d4eec-126">\*The encoding attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is sending its output to a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="d4eec-127">Stattdessen wird die encoding-Eigenschaft für den <xref:System.IO.TextWriter> verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4eec-127">The encoding property on the <xref:System.IO.TextWriter> is used instead.</span></span>
  
 <span data-ttu-id="d4eec-128">Wenn die Ausgabe der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode ein <xref:System.IO.Stream> ist, wird das folgende Attribut ignoriert:</span><span class="sxs-lookup"><span data-stu-id="d4eec-128">The following attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream>:</span></span>  
  
- <span data-ttu-id="d4eec-129">Version: Die Version ist immer 1.0.</span><span class="sxs-lookup"><span data-stu-id="d4eec-129">version: the version is always 1.0</span></span>  
  
- <span data-ttu-id="d4eec-130">Medientyp: Der Medientyp.</span><span class="sxs-lookup"><span data-stu-id="d4eec-130">media-type: the media-type</span></span>  
  
## <a name="escaping-special-characters"></a><span data-ttu-id="d4eec-131">Escapezeichen für Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="d4eec-131">Escaping Special Characters</span></span>  
 <span data-ttu-id="d4eec-132">Das `<xsl:text disable-output-escaping>`-Tag gibt an, ob Sonderzeichen mit Escapezeichen in ein XML-Formular geschrieben werden müssen (z. B. unter Verwendung von `<&lt>` anstelle des `"<"`-Symbols) oder unverändert bleiben.</span><span class="sxs-lookup"><span data-stu-id="d4eec-132">The `<xsl:text disable-output-escaping>` tag is used to indicate whether or not special characters need to be escaped into an XML form (for example, using `<&lt>` in place of the `"<"` symbol) or left in the present condition.</span></span> <span data-ttu-id="d4eec-133">Bei der Transformation in ein `disable-output-escaping`-Objekt oder ein <xref:System.Xml.XmlReader>-Objekt wird das <xref:System.Xml.XmlWriter>-Attribut ignoriert und wirkt sich nicht auf Sonderzeichen aus.</span><span class="sxs-lookup"><span data-stu-id="d4eec-133">The `disable-output-escaping` attribute is ignored when transforming to an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter> object and has no effect on special characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4eec-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4eec-134">See also</span></span>

- [<span data-ttu-id="d4eec-135">Implementierung des XSLT-Prozessors durch die XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="d4eec-135">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
