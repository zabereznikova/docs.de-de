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
ms.openlocfilehash: d6d900ca6868cfffe6b0e5b349321a79c5716c46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347029"
---
# <a name="xml-element-literal-visual-basic"></a>XML-Elementliteral (Visual Basic)

Ein Literalwert, der ein <xref:System.Xml.Linq.XElement> Objekt darstellt.

## <a name="syntax"></a>Syntax

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a>-Komponenten

- `<`

  Erforderlich Öffnet das Startelementtag.

- `name`

  Erforderlich Name des Elements. Das Format ist einer der folgenden:

  - Literaltext für den Elementnamen der Form `[ePrefix:]eName`, wobei Folgendes gilt:

    |-Komponente|Beschreibung|
    |---|---|
    |`ePrefix`|Optional. Das XML-Namespace Präfix für das Element. Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung in der Datei oder auf Projektebene definiert ist, oder ein lokaler XML-Namespace, der in diesem Element oder einem übergeordneten Element definiert ist.|
    |`eName`|Erforderlich Name des Elements. Das Format ist einer der folgenden:<br /><br /> -LiteralText. Siehe [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Eingebetteter Ausdruck der Form `<%= eNameExp %>`. Der Typ `eNameExp` muss `String` oder ein Typ sein, der implizit in <xref:System.Xml.Linq.XName>konvertiert werden kann.|

  - Eingebetteter Ausdruck der Form `<%= nameExp %>`. Der Typ `nameExp` muss `String` oder ein Typ implizit in <xref:System.Xml.Linq.XName>konvertiert werden. Ein eingebetteter Ausdruck ist in einem schließenden Tag eines Elements nicht zulässig.

- `attributeList`

  Optional. Die Liste der im Literalformat deklarierten Attribute.

  `attribute [ attribute ... ]`

  Jede `attribute` verfügt über eine der folgenden Syntaxen:

  - Attribut Zuweisung der Form `[aPrefix:]aName=aValue`, wobei Folgendes gilt:

    |-Komponente|Beschreibung|
    |---|---|
    |`aPrefix`|Optional. Das XML-Namespace Präfix für das Attribut. Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist, oder ein lokaler XML-Namespace, der in diesem Element oder einem übergeordneten Element definiert ist.|
    |`aName`|Erforderlich Der Name des Attributs. Das Format ist einer der folgenden:<br /><br /> -LiteralText. Siehe [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Eingebetteter Ausdruck der Form `<%= aNameExp %>`. Der Typ `aNameExp` muss `String` oder ein Typ sein, der implizit in <xref:System.Xml.Linq.XName>konvertiert werden kann.|
    |`aValue`|Optional. Der Wert des Attributs. Das Format ist einer der folgenden:<br /><br /> -Literaler Text, der in Anführungszeichen eingeschlossen ist.<br />-Eingebetteter Ausdruck der Form `<%= aValueExp %>`. Jeder Typ ist zulässig.|

  - Eingebetteter Ausdruck der Form `<%= aExp %>`.

- `/>`

  Optional. Gibt an, dass das Element ein leeres Element ohne Inhalt ist.

- `>`

  Erforderlich Beendet den Anfang oder das leere Elementtag.

- `elementContents`

  Optional. Der Inhalt des Elements.

  `content [ content ... ]`

  Jede `content` kann eine der folgenden sein:

  - LiteralText. Alle Leerzeichen in `elementContents` werden signifikant, wenn Literaltext vorhanden ist.

  - Eingebetteter Ausdruck der Form `<%= contentExp %>`.

  - XML-Elementliterale.

  - XML-Kommentarliteral. Siehe [XML comment Literal.](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)

  - XML-Verarbeitungs Anweisungs Literale. Siehe [XML Processing Instruction Literale](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).

  - XML-CDATA-Literale. Siehe [XML-CDATA-Literale](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).

- `</[name]>`

  Optional. Stellt das Endtag für das Element dar. Der optionale `name`-Parameter ist nicht zulässig, wenn es sich um das Ergebnis eines eingebetteten Ausdrucks handelt.

## <a name="return-value"></a>Rückgabewert

Ein <xref:System.Xml.Linq.XElement>-Objekt.

## <a name="remarks"></a>Hinweise

Sie können die Literalsyntax des XML-Elements verwenden, um <xref:System.Xml.Linq.XElement> Objekte im Code zu erstellen.

> [!NOTE]
> Ein XML-Literale kann mehrere Zeilen umfassen, ohne Zeilen Fortsetzungs Zeichen zu verwenden. Mit dieser Funktion können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.

Eingebettete Ausdrücke der Formular `<%= exp %>` ermöglichen das Hinzufügen dynamischer Informationen zu einem XML-Elementliterals. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).

Der Visual Basic Compiler konvertiert das XML-Elementliteral in Aufrufe des <xref:System.Xml.Linq.XElement.%23ctor%2A>-Konstruktors und, falls erforderlich, den <xref:System.Xml.Linq.XAttribute.%23ctor%2A>-Konstruktor.

## <a name="xml-namespaces"></a>XML-Namespaces

XML-Namespace Präfixe sind nützlich, wenn Sie XML-Literale mit Elementen aus dem gleichen Namespace mehrmals im Code erstellen müssen. Sie können globale XML-Namespace Präfixe verwenden, die Sie mit der `Imports`-Anweisung definieren, oder lokale Präfixe, die Sie mit der `xmlns:xmlPrefix="xmlNamespace"` Attribut Syntax definieren. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).

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

Beachten Sie, dass der Compiler das Präfix des globalen XML-Namespace in eine Präfix Definition für den XML-Namespace konvertiert hat. Das \<NS: Middle >-Element definiert das XML-Namespace Präfix für das \<NS: Inner1-> Element neu. Das \<NS: Inner2 >-Element verwendet jedoch den Namespace, der von der `Imports`-Anweisung definiert wird.

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement>
- [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [XML-CDATA-Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
