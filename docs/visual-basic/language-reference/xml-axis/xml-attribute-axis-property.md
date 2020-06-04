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
ms.openlocfilehash: 3f60190a949856cb2bbc2eba09d097c09089bea7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408431"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>XML-Attributachseneigenschaft (Visual Basic)
Bietet Zugriff auf den Wert eines Attributs für ein <xref:System.Xml.Linq.XElement> Objekt oder auf das erste Element in einer Auflistung von- <xref:System.Xml.Linq.XElement> Objekten.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Bestandteile  
 `object`  
 Erforderlich. Ein- <xref:System.Xml.Linq.XElement> Objekt oder eine Auflistung von- <xref:System.Xml.Linq.XElement> Objekten.  
  
 .@  
 Erforderlich. Gibt den Anfang einer Attribut Achsen Eigenschaft an.  
  
 <  
 Optional. Gibt den Anfang des Namens des Attributs an, wenn `attribute` in Visual Basic kein gültiger Bezeichner ist.  
  
 `attribute`  
 Erforderlich. Der Name des Attributs, auf das im Format [ `prefix` :] zugegriffen werden soll `name` .  
  
|Teil|BESCHREIBUNG|  
|----------|-----------------|  
|`prefix`|Optional. Das XML-Namespace Präfix für das Attribut. Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.|  
|`name`|Erforderlich. Name des lokalen Attributs. Siehe [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Optional. Bezeichnet das Ende des Namens des Attributs, wenn `attribute` kein gültiger Bezeichner in Visual Basic ist.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Wert von enthält `attribute` . Wenn der Attribut Name nicht vorhanden ist, `Nothing` wird zurückgegeben.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie können eine XML-Attribut Achsen Eigenschaft verwenden, um auf den Wert eines Attributs anhand des Namens aus einem <xref:System.Xml.Linq.XElement> Objekt oder aus dem ersten Element in einer Auflistung von- <xref:System.Xml.Linq.XElement> Objekten zuzugreifen. Sie können einen Attribut Wert anhand des Namens abrufen oder einem Element ein neues Attribut hinzufügen, indem Sie einen neuen Namen mit vorangestelltem @-Bezeichner angeben.  
  
 Wenn Sie auf ein XML-Attribut mit dem @-Bezeichner verweisen, wird der-Attribut Wert als Zeichenfolge zurückgegeben, und Sie müssen die-Eigenschaft nicht explizit angeben <xref:System.Xml.Linq.XAttribute.Value%2A> .  
  
 Die Benennungs Regeln für XML-Attribute unterscheiden sich von den Benennungs Regeln für Visual Basic Bezeichner. Um auf ein XML-Attribut zuzugreifen, das über einen Namen verfügt, der kein gültiger Visual Basic Bezeichner ist, müssen Sie den Namen in spitzen Klammern ( \< and > ) einschließen.  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Der Name in einer Attribut Achsen Eigenschaft kann nur XML-Namespace Präfixe verwenden, die Global mithilfe der-Anweisung deklariert werden `Imports` . Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie die Werte der XML-Attribute aus einer Auflistung von XML-Elementen mit dem Namen "" `type` aus einer Auflistung von XML-Elementen `phone`  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Attribute für ein XML-Element sowohl deklarativ als auch als Teil des XML-Codes erstellt werden, und dynamisch durch Hinzufügen eines Attributs zu einer Instanz eines <xref:System.Xml.Linq.XElement> Objekts. Das `type` Attribut wird deklarativ erstellt, und das `owner` Attribut wird dynamisch erstellt.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Spitze Klammer Syntax verwendet, um den Wert des XML-Attributs mit dem Namen zu erhalten `number-type` , der kein gültiger Bezeichner in Visual Basic ist.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: work`  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Anschließend wird das Präfix des-Namespace verwendet, um ein XML-Literalelement zu erstellen und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen " `ns:name` " zuzugreifen.  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xml.Linq.XElement>
- [XML-Achseneigenschaften](index.md)
- [XML-Literale](../xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
