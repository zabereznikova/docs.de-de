---
title: Migrieren von der XslTransform-Klasse
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 9404d758-679f-4ffb-995d-3d07d817659e
ms.openlocfilehash: 8383d8cb3e5819c46a0716c59323e492bb9add8e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937991"
---
# <a name="migrating-from-the-xsltransform-class"></a>Migrieren von der XslTransform-Klasse

Die Version Visual Studio 2005 wartet mit einer umgestalteten XSLT-Architektur auf. Die <xref:System.Xml.Xsl.XslTransform>-Klasse wurde durch die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ersetzt.

In den folgenden Abschnitten werden einige der Hauptunterschiede zwischen der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse und der <xref:System.Xml.Xsl.XslTransform>-Klasse beschrieben.

## <a name="performance"></a>Leistung

Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse weist eine Reihe von Leistungsverbesserungen auf. Der neue XSLT-Prozessor kompiliert das XSLT-Stylesheet in ein allgemeines Zwischenformat, ähnlich wie dies von der CLR (Common Language Runtime) für andere Programmiersprachen erfolgt. Nachdem ein Stylesheet kompiliert wurde, kann es zwischengespeichert und erneut verwendet werden.

Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse enthält zudem weitere Optimierungen, wodurch sie viel schneller als die <xref:System.Xml.Xsl.XslTransform>-Klasse ist.

> [!NOTE]
> Obwohl die Gesamtleistung der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse besser ist als die der <xref:System.Xml.Xsl.XslTransform>-Klasse, ist die Leistung der <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse möglicherweise langsamer als die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode der <xref:System.Xml.Xsl.XslTransform>-Klasse, wenn sie zum ersten Mal für eine Transformation aufgerufen wird. Dies liegt daran, dass die XSLT-Datei zunächst kompiliert werden muss, bevor sie geladen wird. Weitere Informationen finden Sie im folgenden Blogbeitrag: [XslCompiledTransform Slower than XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform) (XslCompiledTransform langsamer als XslTransform)

## <a name="security"></a>Sicherheit

Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse deaktiviert standardmäßig die Unterstützung für die XSLT-Funktion `document()` und die Erstellung eingebetteter Skripts. Diese Funktionen können durch Erstellen eines <xref:System.Xml.Xsl.XsltSettings>-Objekts aktiviert werden, in dem diese Funktionen aktiviert sind und das an die <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode übergeben wird. Das folgende Beispiel zeigt, wie Sie Skripts aktivieren und eine XSLT-Transformation durchführen können.

[!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
[!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]

Weitere Informationen finden Sie unter [XSLT-Sicherheitsaspekte](../../../../docs/standard/data/xml/xslt-security-considerations.md).

## <a name="new-features"></a>Neue Features

### <a name="temporary-files"></a>Temporäre Dateien

Bei der XSLT-Verarbeitung werden mitunter temporäre Dateien angelegt. Diese temporären Dateien werden z. B. dann erstellt und im Ordner &lt;legacyBold&gt;%TEMP%&lt;/legacyBold&gt; abgelegt, wenn ein Stylesheet Skriptblöcke enthält oder beim Kompilieren die Debugeinstellung auf &lt;legacyBold&gt;true&lt;/legacyBold&gt; gesetzt ist. Es kann vorkommen, dass diese temporären Dateien aufgrund von Timingproblemen nicht wieder gelöscht werden. Dies ist z. B. der Fall, wenn die Dateien von der aktuellen AppDomain oder vom Debugger verwendet werden. Die &lt;legacyBold&gt;Finalize&lt;/legacyBold&gt;-Methode des <xref:System.CodeDom.Compiler.TempFileCollection>-Objekts ist dann nicht in der Lage, die temporären Dateien zu entfernen.

Um sicherzustellen, dass alle temporären Dateien vom Client entfernt werden, können Sie die <xref:System.Xml.Xsl.XslCompiledTransform.TemporaryFiles%2A>-Methode einsetzen, um den Ordner %TEMP% entsprechend aufzuräumen.

### <a name="support-for-the-xsloutput-element-and-xmlwriter"></a>Unterstützung für das "xsl:output"-Element und "XmlWriter"

Die <xref:System.Xml.Xsl.XslTransform>-Klasse hat `xsl:output`-Einstellungen ignoriert, wenn die Transformierenausgabe an ein <xref:System.Xml.XmlWriter>-Objekt gesendet wurde. Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse verfügt über die <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A>-Eigenschaft, die ein <xref:System.Xml.XmlWriterSettings>-Objekt mit den Ausgabeinformationen enthält, die aus dem `xsl:output`-Element des Stylesheets abgeleitet wurden. Das <xref:System.Xml.XmlWriterSettings>-Objekt wird zur Erstellung eines <xref:System.Xml.XmlWriter>-Objekts verwendet, das mit den korrekten Einstellungen versehen ist und an die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode übergeben werden kann. Der folgende C#-Code veranschaulicht dieses Verhalten:

```csharp
// Create the XslTransform object and load the style sheet.
XslCompiledTransform xslt = new XslCompiledTransform();
xslt.Load(stylesheet);

// Load the file to transform.
XPathDocument doc = new XPathDocument(filename);

// Create the writer.
XmlWriter writer = XmlWriter.Create(Console.Out, xslt.OutputSettings);

// Transform the file and send the output to the console.
xslt.Transform(doc, writer);
writer.Close();
```

### <a name="debug-option"></a>Debugoption

Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse kann Debuginformationen generieren, mit denen Sie unter Verwendung des Microsoft Visual Studio-Debuggers Fehler im Stylesheet beheben können. Weitere Informationen finden Sie unter <xref:System.Xml.Xsl.XslCompiledTransform.%23ctor%28System.Boolean%29>.

## <a name="behavioral-differences"></a>Verhaltensunterschiede

### <a name="transforming-to-an-xmlreader"></a>Transformation in einen „XmlReader“

Die <xref:System.Xml.Xsl.XslTransform>-Klasse verfügt über mehrere Transformierenüberladungen, die Transformationsergebnisse in Form eines <xref:System.Xml.XmlReader>-Objekts zurückgeben. Diese Überladungen können verwendet werden, um die Transformationsergebnisse in eine Darstellung im Arbeitsspeicher zu laden (z. B. <xref:System.Xml.XmlDocument> oder <xref:System.Xml.XPath.XPathDocument>), ohne dass dabei unnötig viele Ressourcen für die Serialisierung und Deserialisierung der resultierenden XML-Struktur verbraucht werden. Im folgenden C#-Code wird gezeigt, wie die Transformationsergebnisse in ein <xref:System.Xml.XmlDocument>-Objekt geladen werden:

```csharp
// Load the style sheet
XslTransform xslt = new XslTransform();
xslt.Load("MyStylesheet.xsl");

// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
doc.Load(xslt.Transform(input, (XsltArgumentList)null));
```

Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse bietet keine Unterstützung für das Transformieren in ein <xref:System.Xml.XmlReader>-Objekt. Einen ähnlichen Effekt erreichen Sie aber, indem Sie die <xref:System.Xml.XPath.XPathNavigator.CreateNavigator%2A>-Methode verwenden, um die resultierende XML-Struktur direkt aus einem <xref:System.Xml.XmlWriter> zu laden. Im folgenden C#-Code wird gezeigt, wie Sie die gleiche Aufgabe mit <xref:System.Xml.Xsl.XslCompiledTransform> erledigen können:

```csharp
// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
using (XmlWriter writer = doc.CreateNavigator().AppendChild()) {
    xslt.Transform(input, (XsltArgumentList)null, writer);
}
```

### <a name="discretionary-behavior"></a>Freigegebene Verhaltensweisen

Im W3C-Dokument „XSL Transformations (XSLT) Version 1.0“ gibt es bestimmte Bereiche, bei denen es dem Anbieter der Implementierung freigestellt ist, wie er mit der jeweiligen Situation umgeht. Diese Bereiche werden als "freigegebene Verhaltensweisen" bezeichnet. Es gibt mehrere Bereiche, in denen sich die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse anders verhält als die <xref:System.Xml.Xsl.XslTransform>-Klasse. Weitere Informationen finden Sie unter [Behebbare XSLT-Fehler](../../../../docs/standard/data/xml/recoverable-xslt-errors.md).

### <a name="extension-objects-and-script-functions"></a>Erweiterungsobjekte und Skriptfunktionen

<xref:System.Xml.Xsl.XslCompiledTransform> führt zwei neue Beschränkungen für die Verwendung von Skriptfunktionen ein:

- Von XPath-Ausdrücken aus dürfen nur öffentliche Methoden aufgerufen werden.

- Überladungen können anhand der Anzahl der Argumente voneinander unterschieden werden. Wenn mehrere Überladungen über die gleiche Anzahl von Argumenten verfügen, wird eine Ausnahme ausgelöst.

In <xref:System.Xml.Xsl.XslCompiledTransform> erfolgt beim Kompilieren eine Bindung (Methodennamensuche) an Skriptfunktionen, und Stylesheets, die zusammen mit &lt;legacyBold&gt;XslTranform&lt;/legacyBold&gt; funktioniert haben, können eine Ausnahme auslösen, wenn sie zusammen mit <xref:System.Xml.Xsl.XslCompiledTransform> geladen werden.

<xref:System.Xml.Xsl.XslCompiledTransform> unterstützt die Verwendung von untergeordneten `msxsl:using`- und `msxsl:assembly`-Elementen innerhalb des `msxsl:script`-Elements. Die Elemente `msxsl:using` und `msxsl:assembly` werden verwendet, um zusätzliche Namespaces und Assemblys für die Verwendung im Skriptblock zu deklarieren. Weitere Informationen finden Sie unter [Skriptblöcke, die „msxsl:script“ verwenden](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md).

<xref:System.Xml.Xsl.XslCompiledTransform> verhindert Erweiterungsobjekte, die über mehrere Überladungen mit derselben Anzahl von Argumenten verfügen.

### <a name="msxml-functions"></a>MSXML-Funktionen

Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse wurde um die Unterstützung für zusätzliche MSXML-Funktionen erweitert. In der folgenden Liste werden die neuen oder verbesserten Funktionen aufgeführt:

- msxsl:node-set: Bei <xref:System.Xml.Xsl.XslTransform> musste das Argument der [node-set-Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256197(v=vs.100)) ein Ergebnisstrukturfragment sein. Bei <xref:System.Xml.Xsl.XslCompiledTransform> ist dies nicht erforderlich.

- msxsl:version: Diese Funktion wird in <xref:System.Xml.Xsl.XslCompiledTransform> unterstützt.

- XPath-Erweiterungsfunktionen: die [ms:string-compare-Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256114(v=vs.100)), [ms:utc-Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256474(v=vs.100)), [ms:namespace-uri-Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256231(v=vs.100)), [ms:local-name-Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256055(v=vs.100)), [ms:number-Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256155(v=vs.100)), [ms:format-date-Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256099(v=vs.100)) und [ms:format-time Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms256467(v=vs.100)) werden jetzt unterstützt.

- Schemabezogene XPath-Erweiterungsfunktionen: Diese Funktionen werden von <xref:System.Xml.Xsl.XslCompiledTransform> nicht als native Funktionen unterstützt. Sie können aber als Erweiterungsfunktionen implementiert werden.

## <a name="see-also"></a>Siehe auch

- [XSLT Transformations (XSLT-Transformationen)](../../../../docs/standard/data/xml/xslt-transformations.md)
- [Verwenden der XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
