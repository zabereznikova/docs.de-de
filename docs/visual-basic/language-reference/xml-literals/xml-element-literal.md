---
title: XML-Elementliteral (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralElement
dev_langs:
- VB
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: 32
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
ms.openlocfilehash: c77a1ec3621d056a814b298cd5ee6b8c44c52ec2
ms.lasthandoff: 03/13/2017

---
# <a name="xml-element-literal-visual-basic"></a>XML-Elementliteral (Visual Basic)
Ein Literal, das stellt ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement>  
  
## <a name="syntax"></a>Syntax  
  
```  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a>Teile  
  
-   `<`  
  
     Erforderlich. Öffnet das Startkennzeichen-Element.  
  
-   `name`  
  
     Erforderlich. Name des Elements. Das Format ist eines der folgenden:  
  
    -   Literaltext für den Elementnamen in der Form [`ePrefix``:`]`eName`, wobei:  
  
        |Segment|Beschreibung|  
        |---|---|  
        |`ePrefix`|Optional. XML-Namespacepräfix für das Element. Muss ein globaler XML-Namespace, die mit definiert ist eine `Imports` -Anweisung in der Datei oder auf Projektebene oder ein lokaler XML‑Namespace, der in diesem Element oder einem übergeordneten Element definiert ist.|  
        |`eName`|Erforderlich. Name des Elements. Das Format ist eines der folgenden:<br /><br /> -Literaltext. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Eingebetteter Ausdruck der Form `<%=` e`NameExp` `%>`. Der Typ des `eNameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName>|  
  
    -   Eingebetteter Ausdruck der Form `<%=` `nameExp` `%>`. Der Typ des `nameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> Ein eingebetteter Ausdruck wird in ein Endtag eines Elements nicht zulässig.  
  
-   `attributeList`  
  
     Optional. Liste der Attribute, die in das Literal deklariert werden.  
  
     `attribute [ attribute ... ]`  
  
     Jede `attribute` verfügt über einen der folgenden Syntaxformen:  
  
    -   -Attributzuweisung des Formulars [`aPrefix``:`]`aName``=``aValue`, wobei:  
  
        |Segment|Beschreibung|  
        |---|---|  
        |`aPrefix`|Optional. XML-Namespacepräfix für das Attribut. Muss ein globaler XML-Namespace, die mit definiert ist ein `Imports` -Anweisung oder ein lokaler XML‑Namespace, der in diesem Element oder einem übergeordneten Element definiert ist.|  
        |`aName`|Erforderlich. Der Name des Attributs. Das Format ist eines der folgenden:<br /><br /> -Literaltext. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Eingebetteter Ausdruck der Form `<%=` `aNameExp` `%>`. Der Typ des `aNameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName>|  
        |`aValue`|Optional. Der Wert des Attributs. Das Format ist eines der folgenden:<br /><br /> -Literalen Text in Anführungszeichen eingeschlossen sind.<br />-Eingebetteter Ausdruck der Form `<%=` `aValueExp` `%>`. Jeder Typ ist zulässig.|  
  
    -   Eingebetteter Ausdruck der Form `<%=` `aExp` `%>`.  
  
-   `/>`  
  
     Optional. Gibt an, dass das Element ein leeres Element ohne Inhalt.  
  
-   `>`  
  
     Erforderlich. Beendet das Elementtag ab oder leer.  
  
-   `elementContents`  
  
     Optional. Der Inhalt des Elements.  
  
     `content [ content ... ]`  
  
     Jede `content` kann einer der folgenden sein:  
  
    -   Normaler Text. Der gesamte Leerraum in `elementContents` wird bedeutend, wenn Literaltext vorhanden ist.  
  
    -   Eingebetteter Ausdruck der Form `<%=` `contentExp` `%>`.  
  
    -   XML-Elementliteral.  
  
    -   XML-Kommentarliteral. Finden Sie unter [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).  
  
    -   XML-Verarbeitungsanweisungsliteral. Finden Sie unter [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).  
  
    -   XML CDATA-literal. Finden Sie unter [XML-CDATA-Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).  
  
-   `</`[`name`]`>`  
  
     Dies ist optional. Stellt das Endtag für das Element dar. Das optionale `name` -Parameter ist nicht zulässig, wenn er für einen eingebetteten Ausdruck resultiert.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement>  
  
## <a name="remarks"></a>Hinweise  
 Sie können die XML-Literale Syntax erstellen <xref:System.Xml.Linq.XElement>Objekte in Ihrem Code.</xref:System.Xml.Linq.XElement>  
  
> [!NOTE]
>  Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen. Dieses Feature können Sie Inhalt aus einem XML-Dokument kopieren und Einfügen direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm.  
  
 Eingebettete Ausdrücke der Form `<%=` `exp` `%>` ermöglichen es Ihnen, einem XML-Elementliteral dynamische Informationen hinzugefügt. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert das XML-Elementliteral in Aufrufe an die <xref:System.Xml.Linq.XElement.%23ctor%2A>Konstruktor und, falls erforderlich, die <xref:System.Xml.Linq.XAttribute.%23ctor%2A>Konstruktor.</xref:System.Xml.Linq.XAttribute.%23ctor%2A> </xref:System.Xml.Linq.XElement.%23ctor%2A>  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 XML-Namespacepräfixe sind nützlich, wenn Sie XML-Literale mit Elementen aus demselben Namespace oft in Code erstellen. Können Sie globale XML-Namespacepräfixe verwenden, die mit der `Imports` -Anweisung oder lokale Präfixe, die mit der `xmlns:``xmlPrefix`= "`xmlNamespace`" Attributsyntax. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
 Gemäß den Bereichsregeln für XML-Namespaces haben lokale Präfixe Vorrang gegenüber globalen Präfixen. Wenn ein XML-Literal einen XML-Namespace definiert sind, steht jedoch diesem Namespace nicht auf Ausdrücke, die in einem eingebetteten Ausdruck angezeigt werden. Die eingebettete Ausdruck kann nur auf den globalen XML-Namespace zugreifen.  
  
 Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert jeden globalen XML-Namespace, die von einem XML-literal in eine lokale Namespacedefinition im generierten Code verwendet wird. Globale XML-Namespaces, die nicht verwendet werden, erscheinen nicht im generierten Code.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein einfaches XML-Element zu erstellen, die zwei geschachtelte leere Elemente.  
  
 [!code-vb[VbXMLSamples&20;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 Das Beispiel zeigt den folgenden Text. Beachten Sie, dass das Literal die Struktur der leeren Elemente beibehält.  
  
```  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird das Verwenden von eingebetteter Ausdrücken erstellen Attribute und benennen ein Element veranschaulicht.  
  
 [!code-vb[VbXMLSamples&21;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Anschließend wird das Namespacepräfix verwendet, zum Erstellen von XML-Literalen und abschließende Form des Elements anzeigt.  
  
 [!code-vb[VbXMLSamples&#22;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Beachten Sie, dass der Compiler das Präfix des globalen XML-Namespaces in einer Präfixdefinition für den XML-Namespace konvertiert. Die \<Ns:middle >-Element definiert das XML-Namespacepräfix für den \<Ns:inner1 > Element. Allerdings die \<Ns:inner2 > Element verwendet die von der `Imports` Anweisung.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>   
 [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)   
 [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)   
 [XML-CDATA-Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)   
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
