---
title: XML-Attributachseneigenschaft (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyAttributeAxis
dev_langs:
- VB
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 94211f7c951976426ba17e73df214444a6c227b4
ms.lasthandoff: 03/13/2017

---
# <a name="xml-attribute-axis-property-visual-basic"></a>XML-Attributachseneigenschaft (Visual Basic)
Ermöglicht den Zugriff auf den Wert eines Attributs für ein <xref:System.Xml.Linq.XElement>Objekt oder auf das erste Element in einer Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement>  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Teile  
 `object`  
 Erforderlich. Ein <xref:System.Xml.Linq.XElement>Objekt oder eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement>  
  
 .@  
 Erforderlich. Kennzeichnet den Anfang der Attribute Axis-Eigenschaft.  
  
 <  
 Optional. Kennzeichnet den Beginn des Namens des Attributs bei `attribute` ist kein gültiger Bezeichner in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 `attribute`  
 Erforderlich. Der Name des Attributs des Formulars Zugriff auf [`prefix`:]`name`.  
  
|Segment|Beschreibung|  
|----------|-----------------|  
|`prefix`|Optional. XML-Namespacepräfix für das Attribut. Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.|  
|`name`|Erforderlich. Lokaler Attributname. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Optional. Kennzeichnet das Ende des Namens des Attributs bei `attribute` ist kein gültiger Bezeichner in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die dem Wert des `attribute`. Wenn der Attributname nicht vorhanden ist, `Nothing` zurückgegeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Können Sie Zugriff auf den Wert eines Attributs anhand des Namens von einer XML-Attributachseneigenschaft ein <xref:System.Xml.Linq.XElement>Objekt oder aus dem ersten Element in einer Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement> Sie können einen Attributwert nach Namen abrufen oder hinzufügen ein neues Attributs zu einem Element durch einen neuen Namen mit vorangestellten der @ Bezeichner.  
  
 Bei Verweisen auf ein XML-Attribut mit dem @ Bezeichner, den Wert des Attributs als Zeichenfolge zurückgegeben, und Sie müssen nicht explizit angeben, die <xref:System.Xml.Linq.XAttribute.Value%2A>Eigenschaft.</xref:System.Xml.Linq.XAttribute.Value%2A>  
  
 Die Benennungsregeln für XML-Attribute unterscheiden sich von den Benennungsregeln für [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Bezeichner. Zugriff auf ein XML-Attribut mit dem Namen, der kein gültiger Visual Basic-Bezeichner ist, schließen Sie den Namen in spitzen Klammern (\< und >).  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Der Name in einem Attributachseneigenschaft können nur XML-Namespacepräfixe global deklariert, indem die `Imports` Anweisung. Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie die Werte der XML-Attribute mit dem Namen abrufen `type` aus einer Auflistung von XML-Elementen mit dem Namen `phone`.  
  
 [!code-vb[VbXMLSamples&#12;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Attribute für ein XML-Element sowohl deklarativ als Teil des XML und dynamisch durch Hinzufügen eines Attributs zu einer Instanz von erstellt ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement> Die `type` -Attribut wird deklarativ erstellt und die `owne`R-Attribut wird dynamisch erstellt.  
  
 [!code-vb[VbXMLSamples&#44;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Syntax mit spitzen Klammern zum Abrufen des Wert des XML-Attributs mit dem Namen `number-type`, der kein gültiger Bezeichner in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 [!code-vb[VbXMLSamples&#13;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: work`  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Anschließend wird mithilfe der Namespacepräfix ein XML-literal erstellt und Zugriff auf den ersten untergeordneten Knoten mit dem qualifizierten Namen "`ns:name`".  
  
 [!code-vb[VbXMLSamples&14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>   
 [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
