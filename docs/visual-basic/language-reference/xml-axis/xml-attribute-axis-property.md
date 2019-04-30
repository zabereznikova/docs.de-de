---
title: XML-Attributachseneigenschaft (Visual Basic)
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
ms.openlocfilehash: a7a93608d14bcbec316228b59467b23e9247e043
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62025222"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>XML-Attributachseneigenschaft (Visual Basic)
Ermöglicht den Zugriff auf den Wert eines Attributs für ein <xref:System.Xml.Linq.XElement> Objekt oder auf das erste Element in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.  
  
## <a name="syntax"></a>Syntax  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Teile  
 `object`  
 Erforderlich. Ein <xref:System.Xml.Linq.XElement> Objekt oder eine Auflistung von <xref:System.Xml.Linq.XElement> Objekte.  
  
 .@  
 Erforderlich. Gibt den Anfang einer Attributachseneigenschaft an.  
  
 <  
 Dies ist optional. Kennzeichnet den Anfang des Namens des Attributs bei `attribute` ist kein gültiger Bezeichner im Visual Basic.  
  
 `attribute`  
 Erforderlich. Der Name des Attributs, das die Form den Zugriff auf [`prefix`:]`name`.  
  
|Segment|Beschreibung|  
|----------|-----------------|  
|`prefix`|Dies ist optional. XML-Namespacepräfix für das Attribut. Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.|  
|`name`|Erforderlich. Lokale Attributname. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Dies ist optional. Kennzeichnet das Ende des Namens des Attributs bei `attribute` ist kein gültiger Bezeichner im Visual Basic.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Wert der enthält `attribute`. Wenn Sie der Attributnamen nicht vorhanden ist, `Nothing` zurückgegeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Können Sie eine XML-Attributachseneigenschaft Zugriff auf den Wert eines Attributs aus anhand des Namens einer <xref:System.Xml.Linq.XElement> Objekt oder vom ersten Element in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte. Sie können einen Attributwert Name abrufen oder hinzufügen ein neues Attributs zu einem Element durch einen neuen Namen mit vorangestellten Angabe der @ Bezeichner.  
  
 Bei Verweisen auf ein XML-Attribut mit der @ Bezeichner, den Wert des Attributs als Zeichenfolge zurückgegeben, und Sie müssen nicht explizit angeben, die <xref:System.Xml.Linq.XAttribute.Value%2A> Eigenschaft.  
  
 Die Benennungsregeln für XML-Attribute unterscheiden sich von den Benennungsregeln für Visual Basic-Bezeichner. Zugriff auf ein XML-Attribut mit einem Namen, der kein gültiger Visual Basic-Bezeichner ist, schließen Sie den Namen in spitzen Klammern (\< und >).  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Der Name in einem Attributachseneigenschaft können nur XML-Namespacepräfixe global deklariert werden, indem die `Imports` Anweisung. Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die Werte der XML-Attribute mit dem Namen abrufen `type` aus einer Auflistung von XML-Elementen mit dem Namen `phone`.  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die zum Erstellen von Attributen für ein XML-Element sowohl deklarativ als Teil der XML-Code, und dynamisch durch Hinzufügen eines Attributs zu einer Instanz von einem <xref:System.Xml.Linq.XElement> Objekt. Die `type` -Attribut wird deklarativ erstellt und die `owner` Attribut wird dynamisch erstellt.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Spitze Klammer-Syntax, um den Wert des XML-Attributs mit dem Namen abzurufen `number-type`, das ist nicht in Visual Basic ein gültiger Bezeichner.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: work`  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Klicken Sie dann das Namespacepräfix des Namespace eine XML-literal erstellt und der Zugriff auf den ersten untergeordneten Knoten mit dem qualifizierten Namen verwendet "`ns:name`".  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement>
- [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
