---
title: XML Descendant Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: b2bf524214fa8ecca215d50c198b23d127e3b400
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349445"
---
# <a name="xml-descendant-axis-property-visual-basic"></a>XML-Nachfolgerachseneigenschaft (Visual Basic)

Bietet Zugriff auf die nachfolgenden der folgenden Elemente: ein <xref:System.Xml.Linq.XElement> Objekt, ein <xref:System.Xml.Linq.XDocument> Objekt, eine Auflistung von <xref:System.Xml.Linq.XElement> Objekten oder eine Auflistung von <xref:System.Xml.Linq.XDocument> Objekten.

## <a name="syntax"></a>Syntax

```vb
object...<descendant>
```

## <a name="parts"></a>-Komponenten

`object` ist erforderlich. Ein <xref:System.Xml.Linq.XElement>Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, eine Auflistung von <xref:System.Xml.Linq.XElement>Objekten oder eine Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.

`...<` ist erforderlich. Gibt den Anfang einer untergeordneten Achsen Eigenschaft an.

`descendant` ist erforderlich. Name der untergeordneten Knoten, auf die im Format [`prefix:]name`zugegriffen werden soll.

|-Komponente|Beschreibung|
|----------|-----------------|
|`prefix`|Optional. XML-Namespace Präfix für den Nachfolger Knoten. Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert wird.|
|`name`|Erforderlich Der lokale Name des untergeordneten Knotens. Siehe [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|

`>` ist erforderlich. Bezeichnet das Ende einer Nachfolger Achsen Eigenschaft.

## <a name="return-value"></a>Rückgabewert

Eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.

## <a name="remarks"></a>Hinweise

Sie können eine XML-Nachfolger Achsen Eigenschaft für den Zugriff auf Nachfolger Knoten anhand des Namens aus einem <xref:System.Xml.Linq.XElement>-oder <xref:System.Xml.Linq.XDocument>-Objekt oder aus einer Auflistung von <xref:System.Xml.Linq.XElement>-oder <xref:System.Xml.Linq.XDocument> Objekten verwenden. Verwenden Sie die XML-`Value`-Eigenschaft, um auf den Wert des ersten untergeordneten Knotens in der zurückgegebenen Auflistung zuzugreifen. Weitere Informationen finden Sie unter [XML-Wert Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).

Der Visual Basic-Compiler konvertiert Nachfolger Achsen Eigenschaften in Aufrufe der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Methode.

## <a name="xml-namespaces"></a>XML-Namespaces

Der Name in einer Nachfolger Achsen Eigenschaft kann nur XML-Namespaces verwenden, die Global mit der `Imports`-Anweisung deklariert werden. XML-Namespaces, die lokal in XML-Element Literalen deklariert sind, können nicht verwendet werden. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie auf den Wert des ersten untergeordneten Knotens mit dem Namen `name` und die Werte aller untergeordneten Knoten mit dem Namen `phone` aus dem `contacts`-Objekt zugegriffen wird.

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

Durch diesen Code wird folgender Text angezeigt:

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a>Beispiel

Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Anschließend wird das Präfix des-Namespace verwendet, um ein XML-Literalelement zu erstellen und auf den Wert des ersten untergeordneten Knotens mit dem qualifizierten Namen `ns:name`zuzugreifen.

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

Durch diesen Code wird folgender Text angezeigt:

`Name: Patrick Hines`

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement>
- [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
