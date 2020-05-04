---
title: Implementierung des XSLT-Prozessors durch die XslTransform-Klasse
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 88373fe2-4a6b-44f9-8a62-8a3e348e3a46
ms.openlocfilehash: 73a432db9a3fcb6587184e27e6dfe9ba49010e92
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709607"
---
# <a name="xsltransform-class-implements-the-xslt-processor"></a><span data-ttu-id="8afc0-102">Implementierung des XSLT-Prozessors durch die XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="8afc0-102">XslTransform Class Implements the XSLT Processor</span></span>

> [!NOTE]
> <span data-ttu-id="8afc0-103">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="8afc0-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="8afc0-104">Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen.</span><span class="sxs-lookup"><span data-stu-id="8afc0-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="8afc0-105">Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="8afc0-105">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>

<span data-ttu-id="8afc0-106">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist ein XSLT-Prozessor, der die W3C-Empfehlung zu XSL-Transformationen (XSLT), Version 1.0, implementiert.</span><span class="sxs-lookup"><span data-stu-id="8afc0-106">The <xref:System.Xml.Xsl.XslTransform> class is an XSLT processor implementing the XSL Transformations (XSLT) Version 1.0 recommendation.</span></span> <span data-ttu-id="8afc0-107">Die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode wird zum Auffinden und Lesen von Stylesheets verwendet, und mit der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode wird das angegebene Quelldokument umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="8afc0-107">The <xref:System.Xml.Xsl.XslTransform.Load%2A> method locates and reads style sheets, and the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method transforms the given source document.</span></span> <span data-ttu-id="8afc0-108">Jeder Speicher, der die Schnittstelle <xref:System.Xml.XPath.IXPathNavigable> implementiert, kann als Quelldokument für <xref:System.Xml.Xsl.XslTransform> dienen.</span><span class="sxs-lookup"><span data-stu-id="8afc0-108">Any store that implements the <xref:System.Xml.XPath.IXPathNavigable> interface can be used as the source document for the <xref:System.Xml.Xsl.XslTransform>.</span></span> <span data-ttu-id="8afc0-109">.NET Framework implementiert gegenwärtig die <xref:System.Xml.XPath.IXPathNavigable>-Schnittstelle für <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument> und <xref:System.Xml.XPath.XPathDocument>. Diese Elemente können daher alle als Eingabequelldokumente für eine Transformation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8afc0-109">The .NET Framework currently implements the <xref:System.Xml.XPath.IXPathNavigable> interface on the <xref:System.Xml.XmlDocument>, the <xref:System.Xml.XmlDataDocument>, and the <xref:System.Xml.XPath.XPathDocument>, so all of these can be used as the input source document to a transformation.</span></span>

<span data-ttu-id="8afc0-110">Das <xref:System.Xml.Xsl.XslTransform>-Objekt in .NET Framework unterstützt nur die XSLT 1.0-Spezifikation, die mit dem folgenden Namespace definiert wird:</span><span class="sxs-lookup"><span data-stu-id="8afc0-110">The <xref:System.Xml.Xsl.XslTransform> object in the .NET Framework only supports the XSLT 1.0 specification, defined with the following namespace:</span></span>

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
```

<span data-ttu-id="8afc0-111">Das Stylesheet kann mithilfe der <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode aus einer der folgenden Klassen geladen werden:</span><span class="sxs-lookup"><span data-stu-id="8afc0-111">The style sheet can be loaded, using the <xref:System.Xml.Xsl.XslTransform.Load%2A> method, from one of the following classes:</span></span>

- <span data-ttu-id="8afc0-112">XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8afc0-112">XPathNavigator</span></span>

- <span data-ttu-id="8afc0-113">XmlReader</span><span class="sxs-lookup"><span data-stu-id="8afc0-113">XmlReader</span></span>

- <span data-ttu-id="8afc0-114">Einer Zeichenfolge, die eine URL darstellt.</span><span class="sxs-lookup"><span data-stu-id="8afc0-114">A string representing a URL</span></span>

<span data-ttu-id="8afc0-115">Für jede der zuvor aufgeführten Eingabeklassen ist eine unterschiedliche <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode vorhanden.</span><span class="sxs-lookup"><span data-stu-id="8afc0-115">There is a different <xref:System.Xml.Xsl.XslTransform.Load%2A> method for each of the above input classes.</span></span> <span data-ttu-id="8afc0-116">Manche Methoden nehmen eine Kombination einer dieser Klassen und der <xref:System.Xml.XmlResolver>-Klasse als Argumente an.</span><span class="sxs-lookup"><span data-stu-id="8afc0-116">Some methods take in a combination of one of these classes and the <xref:System.Xml.XmlResolver> class as arguments.</span></span> <span data-ttu-id="8afc0-117"><xref:System.Xml.XmlResolver> wird zum Auffinden von Ressourcen verwendet, auf die mit `<xsl:import>` oder `<xsl:include>` im Stylesheet verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8afc0-117">The <xref:System.Xml.XmlResolver> locates resources referenced by `<xsl:import>` or `<xsl:include>` found in the style sheet.</span></span> <span data-ttu-id="8afc0-118">Die folgenden Methoden akzeptieren eine Zeichenfolge, <xref:System.Xml.XmlReader> oder <xref:System.Xml.XPath.XPathNavigator> als Eingabe.</span><span class="sxs-lookup"><span data-stu-id="8afc0-118">The following methods take a string, <xref:System.Xml.XmlReader>, or <xref:System.Xml.XPath.XPathNavigator> as input.</span></span>

```vb
Overloads Public Sub Load(String)
```

```csharp
public void Load(string);
```

```vb
Overloads Public Sub Load(String, XmlResolver)
```

```csharp
public void Load(string, XmlResolver);
```

```vb
Overloads Public Sub Load(XmlReader, XmlResolver, Evidence)
```

```csharp
public void Load(XmlReader, XmlResolver, Evidence);
```

```vb
Overloads Public Sub Load(XPathNavigator, XmlResolver, Evidence)
```

```csharp
public void Load(XPathNavigator, XmlResolver, Evidence);
```

<span data-ttu-id="8afc0-119">Die meisten der oben aufgeführten <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methoden akzeptieren einen <xref:System.Xml.XmlResolver> als Parameter.</span><span class="sxs-lookup"><span data-stu-id="8afc0-119">Most of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods shown above take an <xref:System.Xml.XmlResolver> as a parameter.</span></span> <span data-ttu-id="8afc0-120"><xref:System.Xml.XmlResolver> wird zum Laden des Stylesheets und ggf. zum Laden weiterer Stylesheets verwendet, auf die im xsl:import-Element und im xsl:include-Element verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8afc0-120">The <xref:System.Xml.XmlResolver> is used to load the style sheet and any style sheet(s) referenced in xsl:import and xsl:include elements.</span></span>

<span data-ttu-id="8afc0-121">Die meisten der <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methoden akzeptieren auch einen Evidence-Parameter.</span><span class="sxs-lookup"><span data-stu-id="8afc0-121">Most of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods also take evidence as a parameter.</span></span> <span data-ttu-id="8afc0-122">Der Evidence-Parameter ist als <xref:System.Security.Policy.Evidence> mit dem Stylesheet verknüpft.</span><span class="sxs-lookup"><span data-stu-id="8afc0-122">The evidence parameter is the <xref:System.Security.Policy.Evidence> that is associated with the style sheet.</span></span> <span data-ttu-id="8afc0-123">Die Sicherheitsebene des Stylesheets beeinflusst die Sicherheitsebene aller nachfolgenden Ressourcen, auf die es verweist, z. B. das enthaltene Skript, alle verwendeten `document()`-Funktionen und alle von <xref:System.Xml.Xsl.XsltArgumentList> verwendeten Erweiterungsobjekte.</span><span class="sxs-lookup"><span data-stu-id="8afc0-123">The security level of the style sheet affects the security level of any subsequent resources it references, such as the script it contains, any `document()` functions it uses, and any extension objects used by the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>

<span data-ttu-id="8afc0-124">Wenn das Stylesheet mithilfe einer <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode geladen wird, die zwar einen URL-Parameter, aber keinen Evidence-Parameter enthält, wird der Beweis des Stylesheets berechnet, indem die gegebene URL mit der jeweiligen Site und Zone kombiniert wird.</span><span class="sxs-lookup"><span data-stu-id="8afc0-124">If the style sheet is loaded using a <xref:System.Xml.Xsl.XslTransform.Load%2A> method that contains a URL parameter and no evidence is provided, the evidence of the style sheet is calculated by combining the given URL with its site and zone.</span></span>

<span data-ttu-id="8afc0-125">Wenn weder URI noch Evidence bereitgestellt werden, gilt der für das Stylesheet festgelegte Evidence als vollständig vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="8afc0-125">If no URI or evidence is provided, then the evidence set for the style sheet is fully trusted.</span></span> <span data-ttu-id="8afc0-126">Laden Sie Stylesheets ausschließlich von vertrauenswürdigen Quellen, und fügen Sie <xref:System.Xml.Xsl.XsltArgumentList> niemals Erweiterungsobjekte hinzu, die nicht vertrauenswürdig sind.</span><span class="sxs-lookup"><span data-stu-id="8afc0-126">Do not load style sheets from untrusted sources, or add untrusted extension objects into the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>

<span data-ttu-id="8afc0-127">Weitere Informationen über Sicherheitsebenen und Beweis sowie die Auswirkungen auf die Skripterstellung finden Sie unter [XSLT-Stylesheetskripterstellung mit \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md).</span><span class="sxs-lookup"><span data-stu-id="8afc0-127">For more information about security levels and evidence and how it affects scripting, see [XSLT Stylesheet Scripting Using \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md).</span></span> <span data-ttu-id="8afc0-128">Informationen über Sicherheitsebenen und Beweis sowie die Auswirkungen auf Erweiterungsobjekte finden Sie unter [„XsltArgumentList“ für Stylesheetparameter und Erweiterungsobjekte](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md).</span><span class="sxs-lookup"><span data-stu-id="8afc0-128">For information about security levels and evidence and how it affects extension objects, see [XsltArgumentList for Style Sheet Parameters and Extension Objects](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md).</span></span>

<span data-ttu-id="8afc0-129">Informationen über Sicherheitsebenen und Beweis sowie die Auswirkungen auf die `document()`-Funktion finden Sie unter [Auflösen von externen XSLT-Stylesheets und Dokumenten](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md).</span><span class="sxs-lookup"><span data-stu-id="8afc0-129">For information about security levels and evidence and how it affects the `document()` function, see [Resolving External XSLT Style Sheets and Documents](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md).</span></span>

<span data-ttu-id="8afc0-130">Ein Stylesheet kann mit einer Reihe von Eingabeparametern ausgestattet werden.</span><span class="sxs-lookup"><span data-stu-id="8afc0-130">A style sheet can be supplied with a number of input parameters.</span></span> <span data-ttu-id="8afc0-131">Das Stylesheet kann auch Funktionen für Erweiterungsobjekte aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8afc0-131">The style sheet can also call functions on extension objects.</span></span> <span data-ttu-id="8afc0-132">Sowohl Parameter als auch Erweiterungsobjekte werden dem Stylesheet mithilfe der <xref:System.Xml.Xsl.XsltArgumentList>-Klasse bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="8afc0-132">Both parameters and extension objects are supplied to the style sheet using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="8afc0-133">Weitere Informationen zum <xref:System.Xml.Xsl.XsltArgumentList> finden Sie unter <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="8afc0-133">For more information about the <xref:System.Xml.Xsl.XsltArgumentList>, see <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>

## <a name="recommended-secure-use-of-xsltransform-class"></a><span data-ttu-id="8afc0-134">Empfehlungen für die sichere Verwendung der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="8afc0-134">Recommended Secure Use of XslTransform Class</span></span>

<span data-ttu-id="8afc0-135">Die Sicherheitsberechtigungen des Stylesheets hängen davon ab, welcher Beweistyp bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8afc0-135">The security privileges of the style sheet depend on the evidence provided.</span></span> <span data-ttu-id="8afc0-136">Die folgende Tabelle fasst den Speicherort des Stylesheets zusammen und beschreibt den bereitzustellenden Beweistyp.</span><span class="sxs-lookup"><span data-stu-id="8afc0-136">The following table summarizes the location of the style sheet and gives an explanation of what type of evidence to give.</span></span>

- <span data-ttu-id="8afc0-137">Für das XSLT-Stylesheet sind keine externen Verweise vorhanden, oder das Stylesheet stammt aus einer vertrauenswürdigen Codebasis.</span><span class="sxs-lookup"><span data-stu-id="8afc0-137">The XSLT style sheet has no external references, or the style sheet comes from a code base that you trust.</span></span>

  - <span data-ttu-id="8afc0-138">Stellen Sie den Beweis aus der Assembly bereit:</span><span class="sxs-lookup"><span data-stu-id="8afc0-138">Provide the evidence from your assembly:</span></span>

    ```vb
    Dim xslt = New XslTransform() xslt.Load(stylesheet, resolver, Me.GetType().Assembly.Evidence)

    XsltTransform xslt = new XslTransform();  xslt.Load(stylesheet, resolver, this.GetType().Assembly.Evidence);
    ```

- <span data-ttu-id="8afc0-139">Das XSLT-Stylesheet stammt aus einer externen Quelle.</span><span class="sxs-lookup"><span data-stu-id="8afc0-139">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="8afc0-140">Der Ursprung der Quelle ist bekannt, und es ist ein überprüfbarer URI vorhanden.</span><span class="sxs-lookup"><span data-stu-id="8afc0-140">The origin of the source is known and there is a verifiable URI.</span></span>

  - <span data-ttu-id="8afc0-141">Verwenden Sie den URI zum Erstellen des Beweises.</span><span class="sxs-lookup"><span data-stu-id="8afc0-141">Create evidence using the URI.</span></span>

    ```vb
    Dim xslt As New XslTransform() Dim ev As Evidence = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri) xslt.Load(stylesheet, resolver, evidence)

    XslTransform xslt = new XslTransform(); Evidence ev = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri); xslt.Load(stylesheet, resolver, evidence);
    ```

- <span data-ttu-id="8afc0-142">Das XSLT-Stylesheet stammt aus einer externen Quelle.</span><span class="sxs-lookup"><span data-stu-id="8afc0-142">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="8afc0-143">Der Ursprung der Quelle ist unbekannt.</span><span class="sxs-lookup"><span data-stu-id="8afc0-143">The origin of the source is not known.</span></span>

  - <span data-ttu-id="8afc0-144">Legen Sie den Beweis auf `null` fest.</span><span class="sxs-lookup"><span data-stu-id="8afc0-144">Set evidence to `null`.</span></span> <span data-ttu-id="8afc0-145">Skriptblöcke werden nicht verarbeitet, die XSLT-Funktion `document()` wird nicht unterstützt, und privilegierte Erweiterungsobjekte sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8afc0-145">Script blocks are not processed, the XSLT `document()` function is not supported, and privileged extension objects are disallowed.</span></span>

    <span data-ttu-id="8afc0-146">Zusätzlich können Sie den `resolver`-Parameter auf `null` setzen. Dadurch wird sichergestellt, dass `xsl:import`- und `xsl:include`-Elemente nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8afc0-146">Additionally, you can also set the `resolver` parameter to `null` This ensures that `xsl:import` and `xsl:include` elements are not processed.</span></span>

- <span data-ttu-id="8afc0-147">Das XSLT-Stylesheet stammt aus einer externen Quelle.</span><span class="sxs-lookup"><span data-stu-id="8afc0-147">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="8afc0-148">Der Ursprung der Quelle ist unbekannt, aber die Skriptunterstützung wird benötigt.</span><span class="sxs-lookup"><span data-stu-id="8afc0-148">The origin of the source is not known, but you require script support.</span></span>

  - <span data-ttu-id="8afc0-149">Fordern Sie einen Beweis vom Aufrufer an.</span><span class="sxs-lookup"><span data-stu-id="8afc0-149">Request evidence from the caller.</span></span>

## <a name="transformation-of-xml-data"></a><span data-ttu-id="8afc0-150">Transformation von XML-Daten</span><span class="sxs-lookup"><span data-stu-id="8afc0-150">Transformation of XML Data</span></span>

<span data-ttu-id="8afc0-151">Nach dem Laden eines Stylesheets wird die Transformation gestartet, indem eine der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methoden aufgerufen und ein Eingabequelldokument bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8afc0-151">Once a style sheet is loaded, the transformation starts by calling one of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> methods and supplying an input source document.</span></span> <span data-ttu-id="8afc0-152">Die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode ist überladen, sodass unterschiedliche Transformationsausgaben möglich sind.</span><span class="sxs-lookup"><span data-stu-id="8afc0-152">The <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is overloaded to provide different transformation outputs.</span></span> <span data-ttu-id="8afc0-153">Die Transformation kann zu folgenden Ausgabeformaten führen:</span><span class="sxs-lookup"><span data-stu-id="8afc0-153">The transformation can result in the following output formats:</span></span>

- <xref:System.Xml.XmlReader>

- <xref:System.Xml.XmlWriter>

- <xref:System.IO.TextWriter>

- <xref:System.IO.Stream>

- <span data-ttu-id="8afc0-154">Zeichenfolgen-URL der Datei</span><span class="sxs-lookup"><span data-stu-id="8afc0-154">String URL of file</span></span>

<span data-ttu-id="8afc0-155">Das letzte Format, die Zeichenfolgen-URL, ermöglicht ein häufig vorkommendes Szenario, bei dem ein in einer URL befindliches Eingabedokument transformiert und dann in die Ausgabe-URL geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="8afc0-155">This last format, the string URL, provides for a commonly used scenario in transforming an input document located in a URL and writing the document to the output URL.</span></span> <span data-ttu-id="8afc0-156">Diese <xref:System.Xml.Xsl.XslTransform.Transform%2A> -Methode ist eine bequeme Methode zum Laden eines XML-Dokuments aus einer Datei, zum Durchführen der XSL-Transformation und zum Schreiben der Ausgabe in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="8afc0-156">This <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is a convenience method to load an XML document from a file, perform the XSLT transformation, and write the output to a file.</span></span> <span data-ttu-id="8afc0-157">Dadurch wird verhindert, dass Sie das Eingabequelldokument erstellen und laden und dann in einen Dateistream schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="8afc0-157">This prevents you from having to create and load the input source document, and then write to a file stream.</span></span> <span data-ttu-id="8afc0-158">Das folgende Codebeispiel veranschaulicht die Verwendung der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode mit der Zeichenfolgen-URL als Eingabe und Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8afc0-158">The following code sample shows this use of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method using the string URL as input and output:</span></span>

```vb
Dim xsltransform As XslTransform = New XslTransform()
xsltransform.Load("favorite.xsl")
xsltransform.Transform("MyDocument.Xml", "TransformResult.xml", Nothing)
```

```csharp
XslTransform xsltransform = new XslTransform();
xsltransform.Load("favorite.xsl");
xsltransform.Transform("MyDocument.xml", "TransformResult.xml", null);
```

## <a name="transforming-a-section-of-an-xml-document"></a><span data-ttu-id="8afc0-159">Transformieren eines Abschnitts eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="8afc0-159">Transforming a Section of an XML Document</span></span>

<span data-ttu-id="8afc0-160">Transformationen werden auf das gesamte Dokument angewendet.</span><span class="sxs-lookup"><span data-stu-id="8afc0-160">Transformations apply to the document as a whole.</span></span> <span data-ttu-id="8afc0-161">Wenn Sie einen anderen Knoten als den Stammknoten des Dokuments übergeben, wird dadurch nicht verhindert, dass im Transformationsprozess auf alle Knoten im geladenen Dokument zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="8afc0-161">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="8afc0-162">Zum Transformieren eines Ergebnisstrukturfragments müssen Sie ein <xref:System.Xml.XmlDocument> erstellen, das nur das Ergebnisstrukturfragment enthält, und dieses <xref:System.Xml.XmlDocument> an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="8afc0-162">To transform a result tree fragment, you must create an <xref:System.Xml.XmlDocument> containing just the result tree fragment and pass that <xref:System.Xml.XmlDocument> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span> <span data-ttu-id="8afc0-163">Im folgenden Beispiel wird eine Transformation für ein Ergebnisstrukturfragment durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="8afc0-163">The following example performs a transformation on a result tree fragment.</span></span>

```vb
Dim xslt As New XslTransform()
xslt.Load("print_root.xsl")
Dim doc As New XmlDocument()
doc.Load("library.xml")
' Create a new document containing just the result tree fragment.
Dim testNode As XmlNode = doc.DocumentElement.FirstChild
Dim tmpDoc As New XmlDocument()
tmpDoc.LoadXml(testNode.OuterXml)
' Pass the document containing the result tree fragment
' to the Transform method.
Console.WriteLine(("Passing " + tmpDoc.OuterXml + " to print_root.xsl"))
xslt.Transform(tmpDoc, Nothing, Console.Out, Nothing)
```

```csharp
XslTransform xslt = new XslTransform();
xslt.Load("print_root.xsl");
XmlDocument doc = new XmlDocument();
doc.Load("library.xml");
// Create a new document containing just the result tree fragment.
XmlNode testNode = doc.DocumentElement.FirstChild;
XmlDocument tmpDoc = new XmlDocument();
tmpDoc.LoadXml(testNode.OuterXml);
// Pass the document containing the result tree fragment
// to the Transform method.
Console.WriteLine("Passing " + tmpDoc.OuterXml + " to print_root.xsl");
xslt.Transform(tmpDoc, null, Console.Out, null);
```

<span data-ttu-id="8afc0-164">Im Beispiel werden die Datei „library.xml“ und die Datei „print_root.xsl“ als Eingabe verwendet, und es wird Folgendes auf der Konsole ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="8afc0-164">The example uses the library.xml and print_root.xsl files as input and outputs the following to the console:</span></span>

```console
Passing <book genre="novel" ISBN="1-861001-57-5"><title>Pride And Prejudice</title></book> to print_root.xsl
Root node is book.
```

<span data-ttu-id="8afc0-165">library.xml</span><span class="sxs-lookup"><span data-stu-id="8afc0-165">library.xml</span></span>

```xml
<library>
  <book genre='novel' ISBN='1-861001-57-5'>
     <title>Pride And Prejudice</title>
  </book>
  <book genre='novel' ISBN='1-81920-21-2'>
     <title>Hook</title>
  </book>
</library>
```

<span data-ttu-id="8afc0-166">print_root.xsl</span><span class="sxs-lookup"><span data-stu-id="8afc0-166">print_root.xsl</span></span>

```xml
<stylesheet version="1.0" xmlns="http://www.w3.org/1999/XSL/Transform" >
  <output method="text" />
  <template match="/">
     Root node is  <value-of select="local-name(//*[position() = 1])" />
  </template>
</stylesheet>
```

## <a name="migration-of-xslt-from-net-framework-version-10-to-net-framework-version-11"></a><span data-ttu-id="8afc0-167">XSLT-Migration von .NET Framework, Version 1.0, auf .NET Framework, Version 1.1</span><span class="sxs-lookup"><span data-stu-id="8afc0-167">Migration of XSLT from .NET Framework version 1.0 to .NET Framework version 1.1</span></span>

<span data-ttu-id="8afc0-168">In der folgenden Tabelle sind die veralteten Methoden von .NET Framework Version 1.0 und die neuen Methoden von .NET Framework Version 1.1 für die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8afc0-168">The following table shows the obsolete .NET Framework version 1.0 methods and new .NET Framework version 1.1 methods for the <xref:System.Xml.Xsl.XslTransform.Load%2A> method.</span></span> <span data-ttu-id="8afc0-169">Mithilfe der neuen Methoden können Sie die Berechtigungen für das Stylesheet einschränken, indem Sie Beweise angeben.</span><span class="sxs-lookup"><span data-stu-id="8afc0-169">The new methods enable you to limit the permissions of the style sheet by specifying evidence.</span></span>

|<span data-ttu-id="8afc0-170">Veraltete Load-Methoden in .NET Framework, Version 1.0</span><span class="sxs-lookup"><span data-stu-id="8afc0-170">Obsolete .NET Framework version 1.0 Load Methods</span></span>|<span data-ttu-id="8afc0-171">Ersetzungs-Load-Methoden in .NET Framework, Version 1.1</span><span class="sxs-lookup"><span data-stu-id="8afc0-171">Replacement .NET Framework version 1.1 Load Methods</span></span>|
|------------------------------------------------------|---------------------------------------------------------|
|<span data-ttu-id="8afc0-172">Load(XPathNavigator input);</span><span class="sxs-lookup"><span data-stu-id="8afc0-172">Load(XPathNavigator input);</span></span><br /><br /> <span data-ttu-id="8afc0-173">Load(XPathNavigator input, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="8afc0-173">Load(XPathNavigator input, XmlResolver resolver);</span></span>|<span data-ttu-id="8afc0-174">Load(XPathNavigator stylesheet, XmlResolver resolver, Evidence evidence);</span><span class="sxs-lookup"><span data-stu-id="8afc0-174">Load(XPathNavigator stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|
|<span data-ttu-id="8afc0-175">Load(IXPathNavigable stylesheet);</span><span class="sxs-lookup"><span data-stu-id="8afc0-175">Load(IXPathNavigable stylesheet);</span></span><br /><br /> <span data-ttu-id="8afc0-176">Load(IXPathNavigable stylesheet, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="8afc0-176">Load(IXPathNavigable stylesheet, XmlResolver resolver);</span></span>|<span data-ttu-id="8afc0-177">Load(IXPathNavigable stylesheet, XmlResolver resolver, Evidence evidence); </span><span class="sxs-lookup"><span data-stu-id="8afc0-177">Load(IXPathNavigable stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|
|<span data-ttu-id="8afc0-178">Load(XmlReader stylesheet);</span><span class="sxs-lookup"><span data-stu-id="8afc0-178">Load(XmlReader stylesheet);</span></span><br /><br /> <span data-ttu-id="8afc0-179">Load(XmlReader stylesheet, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="8afc0-179">Load(XmlReader stylesheet, XmlResolver resolver);</span></span>|<span data-ttu-id="8afc0-180">Load(XmlReader stylesheet, XmlResolver resolver, Evidence evidence);</span><span class="sxs-lookup"><span data-stu-id="8afc0-180">Load(XmlReader stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|

<span data-ttu-id="8afc0-181">In der folgenden Tabelle werden die veralteten und die neuen Methoden für die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="8afc0-181">The following table shows the obsolete and new methods for the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span> <span data-ttu-id="8afc0-182">Die neuen Methoden akzeptieren ein <xref:System.Xml.XmlResolver>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="8afc0-182">The new methods take an <xref:System.Xml.XmlResolver> object.</span></span>

|<span data-ttu-id="8afc0-183">Veraltete Transformieren-Methoden in .NET Framework, Version 1.0</span><span class="sxs-lookup"><span data-stu-id="8afc0-183">Obsolete .NET Framework version 1.0 Transform Methods</span></span>|<span data-ttu-id="8afc0-184">Ersetzungs-Transformieren-Methoden in .NET Framework, Version 1.1</span><span class="sxs-lookup"><span data-stu-id="8afc0-184">Replacement .NET Framework version Transform 1.1 Methods</span></span>|
|-----------------------------------------------------------|--------------------------------------------------------------|
|<span data-ttu-id="8afc0-185">XmlReader Transform(XPathNavigator input, XsltArgumentList args)</span><span class="sxs-lookup"><span data-stu-id="8afc0-185">XmlReader Transform(XPathNavigator input, XsltArgumentList args)</span></span>|<span data-ttu-id="8afc0-186">XmlReader Transform(XPathNavigator  input, XsltArgumentList args, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="8afc0-186">XmlReader Transform(XPathNavigator  input, XsltArgumentList args, XmlResolver resolver)</span></span>|
|<span data-ttu-id="8afc0-187">XmlReader Transform(IXPathNavigable input, XsltArgumentList args)</span><span class="sxs-lookup"><span data-stu-id="8afc0-187">XmlReader Transform(IXPathNavigable input, XsltArgumentList args)</span></span>|<span data-ttu-id="8afc0-188">XmlReader Transform(IXPathNavigable input, XsltArgumentList args, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="8afc0-188">XmlReader Transform(IXPathNavigable input, XsltArgumentList args, XmlResolver resolver)</span></span>|
|<span data-ttu-id="8afc0-189">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output)</span><span class="sxs-lookup"><span data-stu-id="8afc0-189">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output)</span></span>|<span data-ttu-id="8afc0-190">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="8afc0-190">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="8afc0-191">Void Transform(IXPathNavigable input, XsltArgumentList args, XmlWriter output)</span><span class="sxs-lookup"><span data-stu-id="8afc0-191">Void Transform(IXPathNavigable input, XsltArgumentList args, XmlWriter output)</span></span>|<span data-ttu-id="8afc0-192">Void Transform(IXpathNavigable input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="8afc0-192">Void Transform(IXpathNavigable input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="8afc0-193">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output)</span><span class="sxs-lookup"><span data-stu-id="8afc0-193">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output)</span></span>|<span data-ttu-id="8afc0-194">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="8afc0-194">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="8afc0-195">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output)</span><span class="sxs-lookup"><span data-stu-id="8afc0-195">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output)</span></span>|<span data-ttu-id="8afc0-196">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="8afc0-196">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="8afc0-197">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output)</span><span class="sxs-lookup"><span data-stu-id="8afc0-197">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output)</span></span>|<span data-ttu-id="8afc0-198">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="8afc0-198">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="8afc0-199">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output)</span><span class="sxs-lookup"><span data-stu-id="8afc0-199">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output)</span></span>|<span data-ttu-id="8afc0-200">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="8afc0-200">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output, XmlResolver resolver)</span></span>|
|<span data-ttu-id="8afc0-201">Void Transform(String input, String output);</span><span class="sxs-lookup"><span data-stu-id="8afc0-201">Void Transform(String input, String output);</span></span>|<span data-ttu-id="8afc0-202">Void Transform(String input, String output, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="8afc0-202">Void Transform(String input, String output, XmlResolver resolver);</span></span>|

<span data-ttu-id="8afc0-203">Die <xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType>-Eigenschaft ist in .NET Framework Version 1.1 veraltet.</span><span class="sxs-lookup"><span data-stu-id="8afc0-203">The <xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType> property is obsolete in .NET Framework version 1.1.</span></span> <span data-ttu-id="8afc0-204">Verwenden Sie stattdessen die neuen <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Überladungen, die ein <xref:System.Xml.XmlResolver>-Objekt akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="8afc0-204">Instead, use the new <xref:System.Xml.Xsl.XslTransform.Transform%2A> overloads which take an <xref:System.Xml.XmlResolver> object.</span></span>

## <a name="see-also"></a><span data-ttu-id="8afc0-205">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8afc0-205">See also</span></span>

- <xref:System.Xml.Xsl.XslTransform>
- [<span data-ttu-id="8afc0-206">XSLT-Transformationen mit der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="8afc0-206">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="8afc0-207">„XPathNavigator“ in Transformationen</span><span class="sxs-lookup"><span data-stu-id="8afc0-207">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [<span data-ttu-id="8afc0-208">„XPathNodeIterator“ in Transformationen</span><span class="sxs-lookup"><span data-stu-id="8afc0-208">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="8afc0-209">XPathDocument-Eingaben in XslTransform</span><span class="sxs-lookup"><span data-stu-id="8afc0-209">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="8afc0-210">XmlDataDocument-Eingaben in „XslTransform“</span><span class="sxs-lookup"><span data-stu-id="8afc0-210">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
- [<span data-ttu-id="8afc0-211">XmlDocument-Eingaben in „XslTransform“</span><span class="sxs-lookup"><span data-stu-id="8afc0-211">XmlDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
