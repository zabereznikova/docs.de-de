---
title: XML-Elementliteral (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: 54ad162a1a720a1645a3b413e6518d2ccfd37bbe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595915"
---
# <a name="xml-element-literal-visual-basic"></a>XML-Elementliteral (Visual Basic)

Ein Literal, das stellt ein <xref:System.Xml.Linq.XElement> Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a>Teile  
  
-   `<`  
  
     Erforderlich. Öffnet das Elementtag ab.  
  
-   `name`  
  
     Erforderlich. Name des Elements. Das Format ist eines der folgenden:  
  
    -   Literaltext für den Elementnamen, der das Formular `[ePrefix:]eName`, wobei:  
  
        |Segment|Beschreibung|  
        |---|---|  
        |`ePrefix`|Dies ist optional. XML-Namespacepräfix für das Element. Muss ein globaler XML-Namespace, die mit definiert ist ein `Imports` -Anweisung in der Datei oder auf Projektebene oder eine lokale XML-Namespace, die in diesem Element oder ein übergeordnetes Element definiert ist.|  
        |`eName`|Erforderlich. Name des Elements. Das Format ist eines der folgenden:<br /><br /> -Literaltext. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Eingebetteten Ausdruck der Form `<%= eNameExp %>`. Der Typ des `eNameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.|  
  
    -   Eingebetteter Ausdruck der Form `<%= nameExp %>`. Der Typ des `nameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>. Ein eingebetteter Ausdruck wird in ein Endtag eines Elements nicht zulässig.  
  
-   `attributeList`  
  
     Dies ist optional. Liste der Attribute, die in das Literal deklariert werden.  
  
     `attribute [ attribute ... ]`  
  
     Jede `attribute` verfügt über mindestens einen der folgenden Syntaxangaben:  
  
    -   -Attributzuweisung des Formulars `[aPrefix:]aName=aValue`, wobei:  
  
        |Segment|Beschreibung|  
        |---|---|  
        |`aPrefix`|Dies ist optional. XML-Namespacepräfix für das Attribut. Muss ein globaler XML-Namespace, die mit definiert ist ein `Imports` -Anweisung oder eine lokale XML-Namespace, die in diesem Element oder ein übergeordnetes Element definiert ist.|  
        |`aName`|Erforderlich. Der Name des Attributs. Das Format ist eines der folgenden:<br /><br /> -Literaltext. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Eingebetteten Ausdruck der Form `<%= aNameExp %>`. Der Typ des `aNameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.|  
        |`aValue`|Dies ist optional. Der Wert des Attributs. Das Format ist eines der folgenden:<br /><br /> -Wörtlichen Text, die in Anführungszeichen eingeschlossen sind.<br />-Eingebetteten Ausdruck der Form `<%= aValueExp %>`. Alle Typen zulässig.|  
  
    -   Eingebetteter Ausdruck der Form `<%= aExp %>`.  
  
-   `/>`  
  
     Dies ist optional. Gibt an, dass das Element ein leeres Element ohne Inhalt.  
  
-   `>`  
  
     Erforderlich. Beendet das Elementtag ab oder ist leer.  
  
-   `elementContents`  
  
     Dies ist optional. Der Inhalt des Elements.  
  
     `content [ content ... ]`  
  
     Jede `content` kann einen der folgenden sein:  
  
    -   Literaltext. Der gesamte Leerraum in `elementContents` ist wichtig, wenn Literaltext vorhanden ist.  
  
    -   Eingebetteter Ausdruck der Form `<%= contentExp %>`.  
  
    -   XML-Elementliteral.  
  
    -   XML-Kommentarliteral. Finden Sie unter [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).  
  
    -   XML-Verarbeitungsanweisungsliteral. Finden Sie unter [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).  
  
    -   XML CDATA-literal. Finden Sie unter [XML-CDATA-Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).  
  
-   `</[name]>`  
  
     Dies ist optional. Stellt das schließende Tag für das Element dar. Der optionale `name` Parameter ist nicht zulässig, wenn es sich um das Ergebnis eines eingebetteten Ausdrucks ist.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XElement>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die XML-Element-Literalsyntax erstellen <xref:System.Xml.Linq.XElement> Objekte in Ihrem Code.  
  
> [!NOTE]
>  Ein XML-literal kann mehrere Zeilen umfassen, ohne das Zeilenfortsetzungszeichen verwenden. Dieses Feature können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in Visual Basic-Programms.  
  
 Eingebettete Ausdrücke der Form `<%= exp %>` ermöglichen es Ihnen, ein XML-Elementliteral dynamische Informationen hinzugefügt. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Visual Basic-Compiler konvertiert die XML-Elementliteral in Aufrufe an die <xref:System.Xml.Linq.XElement.%23ctor%2A> Konstruktor und, falls dies erforderlich ist, ist die <xref:System.Xml.Linq.XAttribute.%23ctor%2A> Konstruktor.  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 XML-Namespacepräfixe sind nützlich, wenn Sie keine XML-Literale mit Elementen aus dem gleichen Namespace oft in Code zu erstellen. Können Sie globale XML-Namespacepräfixe verwenden, die Sie definieren, mit der `Imports` -Anweisung oder lokale Präfixe, die Sie definieren, mit der `xmlns:xmlPrefix="xmlNamespace"` Attributsyntax. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
 Gemäß den Bereichsregeln für XML-Namespaces haben lokale Präfixe Vorrang vor globalen Präfixe. Wenn ein XML-Literal einen XML-Namespace definiert ist, steht jedoch diesem Namespace nicht auf Ausdrücke, die in einem eingebetteten Ausdruck angezeigt werden. Der eingebettete Ausdruck kann nur auf den globale XML-Namespace zugreifen.  
  
 Visual Basic-Compiler konvertiert jede globale XML-Namespace, der von einem XML-literal in eine lokale Namespacedefinition im generierten Code verwendet wird. Globale XML-Namespaces, die nicht verwendet werden, erscheinen nicht im generierten Code.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie ein einfaches XML-Element zu erstellen, das über zwei geschachtelte leere Elemente verfügt.  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 Das Beispiel zeigt den folgenden Text. Beachten Sie, dass das Literal, die Struktur der leere Elemente beibehält.  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie eingebettete Ausdrücke benennen ein Element, und erstellen Sie Attribute verwenden.  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Anschließend verwendet das Präfix des Namespace, um das Erstellen von XML-Literale und zeigt die endgültige Form des Elements an.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Beachten Sie, dass der Compiler das Präfix des globalen XML-Namespace in eine Präfixdefinition für den XML-Namespace konvertiert. Die \<Ns:middle >-Element definiert das XML-Namespacepräfix für die \<Ns:inner1 > Element. Allerdings die \<Ns:inner2 >-Element verwendet den Namespace, definiert durch die `Imports` Anweisung.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Xml.Linq.XElement>
- [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [XML-CDATA-Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
