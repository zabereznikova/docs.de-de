---
title: XML-Elementliteral
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6a91de4e279816bafd29f46bb4f5422cbd934ff
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400188"
---
# <a name="xml-element-literal-visual-basic"></a>XML-Elementliteral (Visual Basic)

Ein Literalwert, der ein <xref:System.Xml.Linq.XElement> Objekt darstellt.

## <a name="syntax"></a>Syntax

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a>Bestandteile

- `<`

  Erforderlich. Öffnet das Startelementtag.

- `name`

  Erforderlich. Name des Elements. Das Format ist einer der folgenden:

  - Literaltext für den Elementnamen der Form `[ePrefix:]eName` , wobei Folgendes gilt:

    |Teil|BESCHREIBUNG|
    |---|---|
    |`ePrefix`|Optional. Das XML-Namespace Präfix für das Element. Muss ein globaler XML-Namespace sein, der mit einer- `Imports` Anweisung in der Datei oder auf Projektebene definiert ist, oder ein lokaler XML-Namespace, der in diesem Element oder einem übergeordneten Element definiert ist.|
    |`eName`|Erforderlich. Name des Elements. Das Format ist einer der folgenden:<br /><br /> -LiteralText. Siehe [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Eingebetteter Ausdruck des Formulars `<%= eNameExp %>` . Der Typ von `eNameExp` muss `String` oder ein Typ sein, der implizit in konvertierbar ist <xref:System.Xml.Linq.XName> .|

  - Eingebetteter Ausdruck des Formulars `<%= nameExp %>` . Der Typ von `nameExp` muss `String` oder ein Typ sein, der implizit in konvertierbar ist <xref:System.Xml.Linq.XName> . Ein eingebetteter Ausdruck ist in einem schließenden Tag eines Elements nicht zulässig.

- `attributeList`

  Optional. Die Liste der im Literalformat deklarierten Attribute.

  `attribute [ attribute ... ]`

  Jede `attribute` verfügt über eine der folgenden Syntaxen:

  - Attribut Zuweisung im Format `[aPrefix:]aName=aValue` , wobei:

    |Teil|BESCHREIBUNG|
    |---|---|
    |`aPrefix`|Optional. Das XML-Namespace Präfix für das Attribut. Muss ein globaler XML-Namespace sein, der mit einer-Anweisung definiert ist `Imports` , oder ein lokaler XML-Namespace, der in diesem Element oder einem übergeordneten Element definiert ist.|
    |`aName`|Erforderlich. Der Name des Attributs. Das Format ist einer der folgenden:<br /><br /> -LiteralText. Siehe [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Eingebetteter Ausdruck des Formulars `<%= aNameExp %>` . Der Typ von `aNameExp` muss `String` oder ein Typ sein, der implizit in konvertierbar ist <xref:System.Xml.Linq.XName> .|
    |`aValue`|Optional. Der Wert des Attributs. Das Format ist einer der folgenden:<br /><br /> -Literaler Text, der in Anführungszeichen eingeschlossen ist.<br />-Eingebetteter Ausdruck des Formulars `<%= aValueExp %>` . Jeder Typ ist zulässig.|

  - Eingebetteter Ausdruck des Formulars `<%= aExp %>` .

- `/>`

  Optional. Gibt an, dass das Element ein leeres Element ohne Inhalt ist.

- `>`

  Erforderlich. Beendet den Anfang oder das leere Elementtag.

- `elementContents`

  Optional. Der Inhalt des Elements.

  `content [ content ... ]`

  Dabei kann es sich um `content` einen der folgenden handeln:

  - LiteralText. Alle Leerzeichen in `elementContents` werden signifikant, wenn Literaltext vorhanden ist.

  - Eingebetteter Ausdruck des Formulars `<%= contentExp %>` .

  - XML-Elementliterale.

  - XML-Kommentarliteral. Siehe [XML comment Literal.](xml-comment-literal.md)

  - XML-Verarbeitungs Anweisungs Literale. Siehe [XML Processing Instruction Literale](xml-processing-instruction-literal.md).

  - XML-CDATA-Literale. Siehe [XML-CDATA-Literale](xml-cdata-literal.md).

- `</[name]>`

  Optional. Stellt das Endtag für das Element dar. Der optionale- `name` Parameter ist nicht zulässig, wenn es sich um das Ergebnis eines eingebetteten Ausdrucks handelt.

## <a name="return-value"></a>Rückgabewert

Ein <xref:System.Xml.Linq.XElement>-Objekt.

## <a name="remarks"></a>Bemerkungen

Sie können die Literalsyntax des XML-Elements verwenden, um- <xref:System.Xml.Linq.XElement> Objekte in Ihrem Code zu erstellen.

> [!NOTE]
> Ein XML-Literale kann mehrere Zeilen umfassen, ohne Zeilen Fortsetzungs Zeichen zu verwenden. Mit dieser Funktion können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.

Mit eingebetteten Ausdrücken des Formulars `<%= exp %>` können Sie einem XML-Elementliteral dynamische Informationen hinzufügen. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).

Der Visual Basic Compiler konvertiert das XML-Elementliteral in Aufrufe des <xref:System.Xml.Linq.XElement.%23ctor%2A> Konstruktors und, falls erforderlich, den <xref:System.Xml.Linq.XAttribute.%23ctor%2A> Konstruktor.

## <a name="xml-namespaces"></a>XML-Namespaces

XML-Namespace Präfixe sind nützlich, wenn Sie XML-Literale mit Elementen aus dem gleichen Namespace mehrmals im Code erstellen müssen. Sie können globale XML-Namespace Präfixe verwenden, die Sie mithilfe der- `Imports` Anweisung definieren, oder lokale Präfixe, die Sie mithilfe der- `xmlns:xmlPrefix="xmlNamespace"` Attribut Syntax definieren. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../statements/imports-statement-xml-namespace.md).

In Übereinstimmung mit den Bereichs Regeln für XML-Namespaces haben lokale Präfixe Vorrang vor globalen Präfixen. Wenn ein XML-Literale jedoch einen XML-Namespace definiert, ist dieser Namespace für Ausdrücke, die in einem eingebetteten Ausdruck vorkommen, nicht verfügbar. Der eingebettete Ausdruck kann nur auf den globalen XML-Namespace zugreifen.

Der Visual Basic Compiler konvertiert jeden globalen XML-Namespace, der von einem XML-Literalwert verwendet wird, in eine lokale Namespace Definition im generierten Code. Globale XML-Namespaces, die nicht verwendet werden, werden im generierten Code nicht angezeigt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie ein einfaches XML-Element erstellt wird, das über zwei in der Tabelle leere Elemente verfügt.

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

Im Beispiel wird der folgende Text angezeigt. Beachten Sie, dass das Literale die Struktur der leeren Elemente beibehält.

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie eingebettete Ausdrücke verwendet werden, um ein Element zu benennen und Attribute zu erstellen.

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

Durch diesen Code wird folgender Text angezeigt:

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a>Beispiel

Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Anschließend wird das Präfix des-Namespace verwendet, um ein XML-Literalformat zu erstellen, und zeigt die endgültige Form des Elements an.

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

Durch diesen Code wird folgender Text angezeigt:

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

Beachten Sie, dass der Compiler das Präfix des globalen XML-Namespace in eine Präfix Definition für den XML-Namespace konvertiert hat. Das- \<ns:middle> Element definiert das XML-Namespace Präfix für das \<ns:inner1> Element neu. Das- \<ns:inner2> Element verwendet jedoch den Namespace, der durch die-Anweisung definiert wird `Imports` .

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xml.Linq.XElement>
- [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [XML-Kommentarliteral](xml-comment-literal.md)
- [XML-CDATA-Literal](xml-cdata-literal.md)
- [XML-Literale](index.md)
- [Erstellen von XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Eingebettete Ausdrücke in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Imports-Anweisung (XML-Namespace)](../statements/imports-statement-xml-namespace.md)
