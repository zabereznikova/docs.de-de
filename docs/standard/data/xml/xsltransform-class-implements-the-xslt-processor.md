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
# <a name="xsltransform-class-implements-the-xslt-processor"></a>Implementierung des XSLT-Prozessors durch die XslTransform-Klasse

> [!NOTE]
> Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).

Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist ein XSLT-Prozessor, der die W3C-Empfehlung zu XSL-Transformationen (XSLT), Version 1.0, implementiert. Die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode wird zum Auffinden und Lesen von Stylesheets verwendet, und mit der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode wird das angegebene Quelldokument umgewandelt. Jeder Speicher, der die Schnittstelle <xref:System.Xml.XPath.IXPathNavigable> implementiert, kann als Quelldokument für <xref:System.Xml.Xsl.XslTransform> dienen. .NET Framework implementiert gegenwärtig die <xref:System.Xml.XPath.IXPathNavigable>-Schnittstelle für <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument> und <xref:System.Xml.XPath.XPathDocument>. Diese Elemente können daher alle als Eingabequelldokumente für eine Transformation verwendet werden.

Das <xref:System.Xml.Xsl.XslTransform>-Objekt in .NET Framework unterstützt nur die XSLT 1.0-Spezifikation, die mit dem folgenden Namespace definiert wird:

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
```

Das Stylesheet kann mithilfe der <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode aus einer der folgenden Klassen geladen werden:

- XPathNavigator

- XmlReader

- Einer Zeichenfolge, die eine URL darstellt.

Für jede der zuvor aufgeführten Eingabeklassen ist eine unterschiedliche <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode vorhanden. Manche Methoden nehmen eine Kombination einer dieser Klassen und der <xref:System.Xml.XmlResolver>-Klasse als Argumente an. <xref:System.Xml.XmlResolver> wird zum Auffinden von Ressourcen verwendet, auf die mit `<xsl:import>` oder `<xsl:include>` im Stylesheet verwiesen wird. Die folgenden Methoden akzeptieren eine Zeichenfolge, <xref:System.Xml.XmlReader> oder <xref:System.Xml.XPath.XPathNavigator> als Eingabe.

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

Die meisten der oben aufgeführten <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methoden akzeptieren einen <xref:System.Xml.XmlResolver> als Parameter. <xref:System.Xml.XmlResolver> wird zum Laden des Stylesheets und ggf. zum Laden weiterer Stylesheets verwendet, auf die im xsl:import-Element und im xsl:include-Element verwiesen wird.

Die meisten der <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methoden akzeptieren auch einen Evidence-Parameter. Der Evidence-Parameter ist als <xref:System.Security.Policy.Evidence> mit dem Stylesheet verknüpft. Die Sicherheitsebene des Stylesheets beeinflusst die Sicherheitsebene aller nachfolgenden Ressourcen, auf die es verweist, z. B. das enthaltene Skript, alle verwendeten `document()`-Funktionen und alle von <xref:System.Xml.Xsl.XsltArgumentList> verwendeten Erweiterungsobjekte.

Wenn das Stylesheet mithilfe einer <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode geladen wird, die zwar einen URL-Parameter, aber keinen Evidence-Parameter enthält, wird der Beweis des Stylesheets berechnet, indem die gegebene URL mit der jeweiligen Site und Zone kombiniert wird.

Wenn weder URI noch Evidence bereitgestellt werden, gilt der für das Stylesheet festgelegte Evidence als vollständig vertrauenswürdig. Laden Sie Stylesheets ausschließlich von vertrauenswürdigen Quellen, und fügen Sie <xref:System.Xml.Xsl.XsltArgumentList> niemals Erweiterungsobjekte hinzu, die nicht vertrauenswürdig sind.

Weitere Informationen über Sicherheitsebenen und Beweis sowie die Auswirkungen auf die Skripterstellung finden Sie unter [XSLT-Stylesheetskripterstellung mit \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md). Informationen über Sicherheitsebenen und Beweis sowie die Auswirkungen auf Erweiterungsobjekte finden Sie unter [„XsltArgumentList“ für Stylesheetparameter und Erweiterungsobjekte](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md).

Informationen über Sicherheitsebenen und Beweis sowie die Auswirkungen auf die `document()`-Funktion finden Sie unter [Auflösen von externen XSLT-Stylesheets und Dokumenten](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md).

Ein Stylesheet kann mit einer Reihe von Eingabeparametern ausgestattet werden. Das Stylesheet kann auch Funktionen für Erweiterungsobjekte aufrufen. Sowohl Parameter als auch Erweiterungsobjekte werden dem Stylesheet mithilfe der <xref:System.Xml.Xsl.XsltArgumentList>-Klasse bereitgestellt. Weitere Informationen zum <xref:System.Xml.Xsl.XsltArgumentList> finden Sie unter <xref:System.Xml.Xsl.XsltArgumentList>.

## <a name="recommended-secure-use-of-xsltransform-class"></a>Empfehlungen für die sichere Verwendung der XslTransform-Klasse

Die Sicherheitsberechtigungen des Stylesheets hängen davon ab, welcher Beweistyp bereitgestellt wird. Die folgende Tabelle fasst den Speicherort des Stylesheets zusammen und beschreibt den bereitzustellenden Beweistyp.

- Für das XSLT-Stylesheet sind keine externen Verweise vorhanden, oder das Stylesheet stammt aus einer vertrauenswürdigen Codebasis.

  - Stellen Sie den Beweis aus der Assembly bereit:

    ```vb
    Dim xslt = New XslTransform() xslt.Load(stylesheet, resolver, Me.GetType().Assembly.Evidence)

    XsltTransform xslt = new XslTransform();  xslt.Load(stylesheet, resolver, this.GetType().Assembly.Evidence);
    ```

- Das XSLT-Stylesheet stammt aus einer externen Quelle. Der Ursprung der Quelle ist bekannt, und es ist ein überprüfbarer URI vorhanden.

  - Verwenden Sie den URI zum Erstellen des Beweises.

    ```vb
    Dim xslt As New XslTransform() Dim ev As Evidence = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri) xslt.Load(stylesheet, resolver, evidence)

    XslTransform xslt = new XslTransform(); Evidence ev = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri); xslt.Load(stylesheet, resolver, evidence);
    ```

- Das XSLT-Stylesheet stammt aus einer externen Quelle. Der Ursprung der Quelle ist unbekannt.

  - Legen Sie den Beweis auf `null` fest. Skriptblöcke werden nicht verarbeitet, die XSLT-Funktion `document()` wird nicht unterstützt, und privilegierte Erweiterungsobjekte sind nicht zulässig.

    Zusätzlich können Sie den `resolver`-Parameter auf `null` setzen. Dadurch wird sichergestellt, dass `xsl:import`- und `xsl:include`-Elemente nicht verarbeitet werden.

- Das XSLT-Stylesheet stammt aus einer externen Quelle. Der Ursprung der Quelle ist unbekannt, aber die Skriptunterstützung wird benötigt.

  - Fordern Sie einen Beweis vom Aufrufer an.

## <a name="transformation-of-xml-data"></a>Transformation von XML-Daten

Nach dem Laden eines Stylesheets wird die Transformation gestartet, indem eine der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methoden aufgerufen und ein Eingabequelldokument bereitgestellt wird. Die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode ist überladen, sodass unterschiedliche Transformationsausgaben möglich sind. Die Transformation kann zu folgenden Ausgabeformaten führen:

- <xref:System.Xml.XmlReader>

- <xref:System.Xml.XmlWriter>

- <xref:System.IO.TextWriter>

- <xref:System.IO.Stream>

- Zeichenfolgen-URL der Datei

Das letzte Format, die Zeichenfolgen-URL, ermöglicht ein häufig vorkommendes Szenario, bei dem ein in einer URL befindliches Eingabedokument transformiert und dann in die Ausgabe-URL geschrieben wird. Diese <xref:System.Xml.Xsl.XslTransform.Transform%2A> -Methode ist eine bequeme Methode zum Laden eines XML-Dokuments aus einer Datei, zum Durchführen der XSL-Transformation und zum Schreiben der Ausgabe in eine Datei. Dadurch wird verhindert, dass Sie das Eingabequelldokument erstellen und laden und dann in einen Dateistream schreiben müssen. Das folgende Codebeispiel veranschaulicht die Verwendung der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode mit der Zeichenfolgen-URL als Eingabe und Ausgabe:

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

## <a name="transforming-a-section-of-an-xml-document"></a>Transformieren eines Abschnitts eines XML-Dokuments

Transformationen werden auf das gesamte Dokument angewendet. Wenn Sie einen anderen Knoten als den Stammknoten des Dokuments übergeben, wird dadurch nicht verhindert, dass im Transformationsprozess auf alle Knoten im geladenen Dokument zugegriffen wird. Zum Transformieren eines Ergebnisstrukturfragments müssen Sie ein <xref:System.Xml.XmlDocument> erstellen, das nur das Ergebnisstrukturfragment enthält, und dieses <xref:System.Xml.XmlDocument> an die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode übergeben. Im folgenden Beispiel wird eine Transformation für ein Ergebnisstrukturfragment durchgeführt.

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

Im Beispiel werden die Datei „library.xml“ und die Datei „print_root.xsl“ als Eingabe verwendet, und es wird Folgendes auf der Konsole ausgegeben:

```console
Passing <book genre="novel" ISBN="1-861001-57-5"><title>Pride And Prejudice</title></book> to print_root.xsl
Root node is book.
```

library.xml

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

print_root.xsl

```xml
<stylesheet version="1.0" xmlns="http://www.w3.org/1999/XSL/Transform" >
  <output method="text" />
  <template match="/">
     Root node is  <value-of select="local-name(//*[position() = 1])" />
  </template>
</stylesheet>
```

## <a name="migration-of-xslt-from-net-framework-version-10-to-net-framework-version-11"></a>XSLT-Migration von .NET Framework, Version 1.0, auf .NET Framework, Version 1.1

In der folgenden Tabelle sind die veralteten Methoden von .NET Framework Version 1.0 und die neuen Methoden von .NET Framework Version 1.1 für die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode aufgeführt. Mithilfe der neuen Methoden können Sie die Berechtigungen für das Stylesheet einschränken, indem Sie Beweise angeben.

|Veraltete Load-Methoden in .NET Framework, Version 1.0|Ersetzungs-Load-Methoden in .NET Framework, Version 1.1|
|------------------------------------------------------|---------------------------------------------------------|
|Load(XPathNavigator input);<br /><br /> Load(XPathNavigator input, XmlResolver resolver);|Load(XPathNavigator stylesheet, XmlResolver resolver, Evidence evidence);|
|Load(IXPathNavigable stylesheet);<br /><br /> Load(IXPathNavigable stylesheet, XmlResolver resolver);|Load(IXPathNavigable stylesheet, XmlResolver resolver, Evidence evidence); |
|Load(XmlReader stylesheet);<br /><br /> Load(XmlReader stylesheet, XmlResolver resolver);|Load(XmlReader stylesheet, XmlResolver resolver, Evidence evidence);|

In der folgenden Tabelle werden die veralteten und die neuen Methoden für die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode aufgelistet. Die neuen Methoden akzeptieren ein <xref:System.Xml.XmlResolver>-Objekt.

|Veraltete Transformieren-Methoden in .NET Framework, Version 1.0|Ersetzungs-Transformieren-Methoden in .NET Framework, Version 1.1|
|-----------------------------------------------------------|--------------------------------------------------------------|
|XmlReader Transform(XPathNavigator input, XsltArgumentList args)|XmlReader Transform(XPathNavigator  input, XsltArgumentList args, XmlResolver resolver)|
|XmlReader Transform(IXPathNavigable input, XsltArgumentList args)|XmlReader Transform(IXPathNavigable input, XsltArgumentList args, XmlResolver resolver)|
|Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output)|Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)|
|Void Transform(IXPathNavigable input, XsltArgumentList args, XmlWriter output)|Void Transform(IXpathNavigable input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)|
|Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output)|Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output, XmlResolver resolver)|
|Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output)|Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output, XmlResolver resolver)|
|Void Transform(XPathNavigator input, XsltArgumentList args, Stream output)|Void Transform(XPathNavigator input, XsltArgumentList args, Stream output, XmlResolver resolver)|
|Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output)|Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output, XmlResolver resolver)|
|Void Transform(String input, String output);|Void Transform(String input, String output, XmlResolver resolver);|

Die <xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType>-Eigenschaft ist in .NET Framework Version 1.1 veraltet. Verwenden Sie stattdessen die neuen <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Überladungen, die ein <xref:System.Xml.XmlResolver>-Objekt akzeptieren.

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Xsl.XslTransform>
- [XSLT-Transformationen mit der XslTransform-Klasse](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [„XPathNavigator“ in Transformationen](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [„XPathNodeIterator“ in Transformationen](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [XPathDocument-Eingaben in XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [XmlDataDocument-Eingaben in „XslTransform“](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
- [XmlDocument-Eingaben in „XslTransform“](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
