---
title: XML Attribute Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 109c4b45a5e3ed4e3e4db49687df5cb127a5e0c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352674"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>XML-Attributachseneigenschaft (Visual Basic)
Bietet Zugriff auf den Wert eines Attributs für ein <xref:System.Xml.Linq.XElement> Objekt oder auf das erste Element in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekten.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>-Komponenten  
 `object`  
 Erforderlich Ein <xref:System.Xml.Linq.XElement>-Objekt oder eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.  
  
 .@  
 Erforderlich Gibt den Anfang einer Attribut Achsen Eigenschaft an.  
  
 <  
 Optional. Gibt den Anfang des Namens des Attributs an, wenn `attribute` in Visual Basic kein gültiger Bezeichner ist.  
  
 `attribute`  
 Erforderlich Der Name des Attributs, auf das mit dem Format [`prefix`:]`name`zugegriffen werden soll.  
  
|-Komponente|Beschreibung|  
|----------|-----------------|  
|`prefix`|Optional. Das XML-Namespace Präfix für das Attribut. Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.|  
|`name`|Erforderlich Name des lokalen Attributs. Siehe [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Optional. Gibt das Ende des Namens des Attributs an, wenn `attribute` in Visual Basic kein gültiger Bezeichner ist.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Wert `attribute`enthält. Wenn der Attribut Name nicht vorhanden ist, wird `Nothing` zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine XML-Attribut Achsen Eigenschaft verwenden, um auf den Wert eines Attributs anhand des Namens aus einem <xref:System.Xml.Linq.XElement> Objekt oder aus dem ersten Element in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekten zuzugreifen. Sie können einen Attribut Wert anhand des Namens abrufen oder einem Element ein neues Attribut hinzufügen, indem Sie einen neuen Namen mit vorangestelltem @-Bezeichner angeben.  
  
 Wenn Sie auf ein XML-Attribut mit dem @-Bezeichner verweisen, wird der-Attribut Wert als Zeichenfolge zurückgegeben, und Sie müssen die <xref:System.Xml.Linq.XAttribute.Value%2A>-Eigenschaft nicht explizit angeben.  
  
 Die Benennungs Regeln für XML-Attribute unterscheiden sich von den Benennungs Regeln für Visual Basic Bezeichner. Um auf ein XML-Attribut zuzugreifen, das über einen Namen verfügt, der kein gültiger Visual Basic Bezeichner ist, müssen Sie den Namen in spitzen Klammern (\< und >) einschließen.  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Der Name in einer Attribut Achsen Eigenschaft kann nur XML-Namespace Präfixe verwenden, die Global mithilfe der `Imports`-Anweisung deklariert werden. Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Werte der XML-Attribute mit dem Namen `type` aus einer Auflistung von XML-Elementen, die `phone`benannt werden, angezeigt werden.  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Attribute für ein XML-Element sowohl deklarativ als auch als Teil des XML-Codes erstellt werden, und dynamisch durch Hinzufügen eines Attributs zu einer Instanz eines <xref:System.Xml.Linq.XElement> Objekts. Das `type`-Attribut wird deklarativ erstellt, und das `owner`-Attribut wird dynamisch erstellt.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Spitze Klammer Syntax verwendet, um den Wert des XML-Attributs mit dem Namen "`number-type`" zu erhalten. Dies ist kein gültiger Bezeichner in Visual Basic.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: work`  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Anschließend wird das Präfix des-Namespace verwendet, um ein XML-Literalelement zu erstellen und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen "`ns:name`" zuzugreifen.  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement>
- [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
