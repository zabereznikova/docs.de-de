---
title: Ergebnisstrukturfragment in Transformationen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: df363480-ba02-4233-9ddf-8434e421c4f1
ms.openlocfilehash: e454c1194e8c280042857f106e22d0d0509417e3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156360"
---
# <a name="result-tree-fragment-in-transformations"></a>Ergebnisstrukturfragment in Transformationen

> [!NOTE]
> Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md).

 Ergebnisstrukturfragmente sind lediglich spezielle Knotengruppentypen. Für sie können dieselben Funktionen ausgeführt werden wie für Knotengruppen. Außerdem können Ergebnisstrukturfragmente mit der `node-set()`-Funktion in Knotengruppen konvertiert und anschließend überall verwendet werden, wo eine Knotengruppe verwendet werden kann.

 Ein Ergebnisstrukturfragment wird erstellt, wenn ein `<xsl:variable>`-Element oder ein `<xsl:param>`-Element in einem Stylesheet auf eine bestimmte Art und Weise verwendet wurde. Im Folgenden wird die Syntax für das `variable`-Element und das `parameter`-Element dargestellt:

```xml
<xsl:param name=Qname select= XPath Expression >
    template body
</xsl:param>

<xsl:variable name=Qname select=XPath Expression >
    template body
</xsl:variable>
```

Beim `parameter`-Element kann der Wert dem `Qname` (qualifizierter Name) auf verschiedene Weise zugeordnet werden. Sie können dem Parameter einen Standardwert zuweisen, indem Inhalt aus dem XPath-Ausdruck im `select`-Attribut zurückgegeben wird, oder indem dem Parameter der Inhalt des Vorlagenkörpers zugewiesen wird.

Dem `variable`-Element kann der Wert ebenfalls auf verschiedene Weise zugewiesen werden. Die Zuordnung kann erfolgen, indem der Inhalt aus dem XPath-Ausdruck im `select`-Attribut zurückgegeben wird, oder indem der Inhalt des Vorlagenkörpers zugewiesen wird.

Wenn bei einem `parameter`-Element und einem `variable`-Element der Wert durch den XPath-Ausdruck zugeordnet wird, wird einer der vier XPath-Grundtypen zurückgegeben: Boolesch, Zeichenfolge, Zahl oder Knotengruppe. Wenn der Wert aus einem Vorlagenkörper mit Inhalt stammt, wird kein XPath-Datentyp zurückgegeben, sondern ein Ergebnisstrukturfragment.

Nur wenn eine Variable nicht an einen der vier XPath-Grunddatentypen, sondern an ein Ergebnisstrukturfragment gebunden ist, gibt eine XPath-Abfrage einen Typ zurück, der nicht zu den vier XPath-Objekttypen gehört. Das Verhalten von Ergebnisstrukturfragmenten wird in der [W3C-Spezifikation](https://www.w3.org/TR/xslt-10/), [Abschnitt 11.1, „Result Tree Fragments“](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments), bis [Abschnitt 11.6, „Passing Parameters to Templates“](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates), erörtert. Darüber hinaus werden in [Abschnitt 1, „Introduction“](https://www.w3.org/TR/xslt-10/#section-Introduction) Möglichkeiten erläutert, wie Vorlagen auch Elemente aus dem XSLT-Namespace enthalten können, die Ergebnisstrukturfragmente zurückgeben oder erstellen.

Ein Ergebnisstrukturfragment verhält sich im Grunde wie eine Knotengruppe mit lediglich einem einzelnen Stammknoten. Die übrigen zurückgegebenen Knoten sind jedoch untergeordnete Knoten. Zur programmgesteuerten Anzeige der untergeordneten Knoten kopieren Sie das Ergebnisstrukturfragment mithilfe des `<xsl:copy-of>`-Elements in die Ergebnisstruktur. Beim Ausführen des copy-of-Vorgangs werden auch alle untergeordneten Knoten der Reihe nach in die Ergebnisstruktur kopiert. Erst wenn `copy` oder `copy-of` verwendet wird, ist ein Ergebnisstrukturfragment Teil der Ergebnisstruktur oder der Transformationsausgabe.

Zum Durchlaufen der zurückgegebenen Knoten eines Ergebnisstrukturfragments wird ein <xref:System.Xml.XPath.XPathNavigator> verwendet. Im folgenden Codebeispiel wird dargestellt, wie ein Ergebnisstrukturfragment in einem Stylesheet erstellt wird. Dabei wird die Funktion mit einem Parameter `fragment` aufgerufen, der XML enthält.

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:var name="fragment">
        <node1>
            <node2/>
        </node1>
    <xsl:var>

  <msxsl:script language="C#" implements-prefix="user">
    function NodeFragment(XPathNavigator nav)
    {
      if (nav.HasSelection == false)
        XPathNavigator.MoveToNext();
      return;
    }
  </msxsl:script>

    <xsl:template match="/">
            <xsl:value-of select="user:NodeFragment(msxml:node-set($fragment))"/>
    </xsl:template>
</xsl:stylesheet>
```

Im nächsten Beispiel wird eine Variable im RTF-Format (Rich Text Format) und damit ein Typ eines Ergebnisstrukturfragments dargestellt, der nicht in eine Knotengruppe konvertiert wurde. Stattdessen erfolgt eine Übergabe an eine Skriptfunktion, und <xref:System.Xml.XPath.XPathNavigator> wird zum Navigieren durch die Knoten verwendet.

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNavigator nav)
    {
        bool b = nav.MoveToFirstChild();
        if (b)
            return nav.Value;
        else
            return "Does not exist";
    }

]]>

</msxsl:script>

<xsl:template match="/">
    <first_book>
        <xsl:value-of select="user:func($node-fragment)"/>
    </first_book>
</xsl:template>

</xsl:stylesheet>
```

In der folgenden Ausgabe wird das Ergebnis der XML-Transformation mit diesem Stylesheet dargestellt.

## <a name="output"></a>Output

```xml
<first_book xmlns:user="urn:books">Book1</first_book>
```

Wie oben angegeben, können Sie mit der `node-set`-Funktion ein Ergebnisstrukturfragment in eine Knotengruppe konvertieren. Der resultierende Knoten enthält immer einen einzelnen Knoten, der den Stammknoten der Struktur darstellt. Wenn Sie ein Ergebnisstrukturfragment in eine Knotengruppe konvertieren, können Sie es überall verwenden, wo reguläre Knotengruppen verwendet werden, z. B. in einer for-each`select`-Anweisung oder im Wert eines -Attributs. Im folgenden Beispiel wird die Umwandlung eines Fragments in eine Knotengruppe und die anschließende Verwendung als Knotengruppe dargestellt:

`<xsl:for-each select="msxsl:node-set($node-fragment)">`

`<xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>`

Wenn Sie ein Fragment in eine Knotengruppe konvertieren, wird <xref:System.Xml.XPath.XPathNavigator> nicht mehr zum Navigieren durch die Knoten verwendet. Stattdessen verwenden Sie für Knotengruppen <xref:System.Xml.XPath.XPathNodeIterator>.

Im folgenden Beispiel handelt es sich bei `$var` um eine Variable, die im Stylesheet eine Knotenstruktur darstellt. Die „for-each“-Anweisung in Verbindung mit der `node-set`-Funktion ermöglicht es Benutzern, diese Struktur wie eine Knotengruppe zu durchlaufen.

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:variable name="states">
        <node1>AL</node1>
        <node1>CA</node1>
        <node1>CO</node1>
        <node1>WA</node1>
    </xsl:variable>

    <xsl:template match="/">
            <xsl:for-each select="msxsl:node-set($states)"/>
    </xsl:template>
</xsl:stylesheet>
```

Im nächsten Beispiel wird eine RTF-Variable und damit ein Ergebnisstrukturfragmenttyp dargestellt, der in eine Knotengruppe konvertiert und anschließend als XPathNodeIterator an eine Skriptfunktion übergeben wird.

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNodeIterator it)
    {
        it.MoveNext();
        return it.Current.Value;
        //it.Current returns XPathNavigator positioned on the current node
    }

]]>

</msxsl:script>
<xsl:template match="/">
    <books>
        <xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>
    </books>
</xsl:template>

</xsl:stylesheet>
```

Nachfolgend wird das Ergebnis der XML-Transformation mit diesem Stylesheet dargestellt:

```xml
<books xmlns:user="urn:books">Book1Book2Book3Book4</books>
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XPath.XPathNodeIterator>
- [XSLT-Transformationen mit der XslTransform-Klasse](xslt-transformations-with-the-xsltransform-class.md)
- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](xsltransform-class-implements-the-xslt-processor.md)
