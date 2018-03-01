---
title: XML-Attributachseneigenschaft (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a286c70f57128d0406b3a300610fea5e1c44b32d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xml-attribute-axis-property-visual-basic"></a>XML-Attributachseneigenschaft (Visual Basic)
Bietet Zugriff auf den Wert eines Attributs für ein <xref:System.Xml.Linq.XElement> Objekt oder auf das erste Element in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.  
  
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
 Erforderlich. Kennzeichnet den Anfang der Attribute Axis-Eigenschaft.  
  
 <  
 Dies ist optional. Kennzeichnet den Anfang des Namens des Attributs Wenn `attribute` ist kein gültiger Bezeichner in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
 `attribute`  
 Erforderlich. Der Name des Attributs des Formulars den Zugriff auf [`prefix`:]`name`.  
  
|Segment|Beschreibung|  
|----------|-----------------|  
|`prefix`|Dies ist optional. XML-Namespacepräfix für das Attribut. Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.|  
|`name`|Erforderlich. Lokale Attributname. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Dies ist optional. Kennzeichnet das Ende des Namens des Attributs Wenn `attribute` ist kein gültiger Bezeichner in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Wert der enthält `attribute`. Wenn der Attributname nicht vorhanden ist, `Nothing` wird zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Können Sie den Wert eines Attributs anhand des Namens aus den Zugriff auf ein XML-Attributachseneigenschaft ein <xref:System.Xml.Linq.XElement> Objekt oder vom ersten Element in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte. Sie können einen Attributwert anhand des Namens abrufen oder hinzufügen ein neues Attributs auf ein Element unter Angabe eines neuen Namens vorangestellt der @ Bezeichner.  
  
 Bei Verweisen auf ein XML-Attribut mit dem @ Bezeichner, den Wert des Attributs als Zeichenfolge zurückgegeben, und Sie müssen nicht explizit angeben der <xref:System.Xml.Linq.XAttribute.Value%2A> Eigenschaft.  
  
 Die Benennungsregeln für XML-Attribute unterscheiden sich von den Benennungsregeln für [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Bezeichner. Zugriff auf ein XML-Attribut mit dem Namen, der kein gültiger Visual Basic-Bezeichner ist, schließen Sie den Namen in spitzen Klammern (\< und >).  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Der Name in einem Attributachseneigenschaft können nur XML-Namespacepräfixe global deklariert werden, mithilfe der `Imports` Anweisung. Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie Sie die Werte der XML-Attribute mit dem Namen abrufen `type` aus einer Auflistung von XML-Elementen mit dem Namen sind `phone`.  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie Attribute für ein XML-Element beide deklarativ als Teil des XML- und dynamisch durch Hinzufügen eines Attributs zu einer Instanz von erstellt ein <xref:System.Xml.Linq.XElement> Objekt. Die `type` -Attribut wird deklarativ erstellt und die `owner` -Attribut wird dynamisch erstellt.  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Spitze Klammer-Syntax zum Abrufen des Werts der XML-Attribut mit dem Namen `number-type`, der kein gültiger Bezeichner in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: work`  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Es verwendet dann das Namespacepräfix ein XML-literal erstellt und Zugriff auf den ersten untergeordneten Knoten mit dem qualifizierten Namen "`ns:name`".  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>  
 [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
