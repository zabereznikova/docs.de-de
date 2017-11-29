---
title: XML-Elementliteral (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: "32"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de5825a6af1dd1b93c3c85651125cf817dc564f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
  
     Erforderlich. Öffnet beginnend Element-Tag.  
  
-   `name`  
  
     Erforderlich. Name des Elements. Das Format ist eines der folgenden:  
  
    -   Literaltext für den Elementnamen des Formulars `[ePrefix:]eName`, wobei:  
  
        |Segment|Beschreibung|  
        |---|---|  
        |`ePrefix`|Dies ist optional. XML-Namespacepräfix für das Element. Muss ein globaler XML-Namespace, die mit definiert ist ein `Imports` -Anweisung in der Datei oder auf Projektebene oder eine lokale XML-Namespace, die in diesem Element oder einem übergeordneten Element definiert ist.|  
        |`eName`|Erforderlich. Name des Elements. Das Format ist eines der folgenden:<br /><br /> -Literaltext. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Eingebetteter Ausdruck der Form `<%= eNameExp %>`. Der Typ des `eNameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.|  
  
    -   Eingebetteter Ausdruck der Form `<%= nameExp %>`. Der Typ des `nameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>. Ein eingebetteter Ausdruck wird in ein Endtag eines Elements nicht zulässig.  
  
-   `attributeList`  
  
     Dies ist optional. Liste der Attribute, die in das Literal deklariert werden.  
  
     `attribute [ attribute ... ]`  
  
     Jede `attribute` verfügt über einen der folgenden Syntaxangaben:  
  
    -   Zuweisung des Formulars-Attribut `[aPrefix:]aName=aValue`, wobei:  
  
        |Segment|Beschreibung|  
        |---|---|  
        |`aPrefix`|Dies ist optional. XML-Namespacepräfix für das Attribut. Muss ein globaler XML-Namespace, die mit definiert ist ein `Imports` -Anweisung oder ein lokaler XML-Namespace, die in diesem Element oder einem übergeordneten Element definiert ist.|  
        |`aName`|Erforderlich. Der Name des Attributs. Das Format ist eines der folgenden:<br /><br /> -Literaltext. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Eingebetteter Ausdruck der Form `<%= aNameExp %>`. Der Typ des `aNameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.|  
        |`aValue`|Dies ist optional. Der Wert des Attributs. Das Format ist eines der folgenden:<br /><br /> -Wörtlichen Text, in Anführungszeichen eingeschlossen.<br />-Eingebetteter Ausdruck der Form `<%= aValueExp %>`. Jeder Typ ist zulässig.|  
  
    -   Eingebetteter Ausdruck der Form `<%= aExp %>`.  
  
-   `/>`  
  
     Dies ist optional. Gibt an, dass das Element ein leeres Element ohne Inhalt ist.  
  
-   `>`  
  
     Erforderlich. Beendet die Element-Tag ab oder leer sein.  
  
-   `elementContents`  
  
     Dies ist optional. Der Inhalt des Elements.  
  
     `content [ content ... ]`  
  
     Jede `content` kann eines der folgenden sein:  
  
    -   Literaltext. Der Leerraum in `elementContents` ist wichtig, wenn Literaltext vorhanden ist.  
  
    -   Eingebetteter Ausdruck der Form `<%= contentExp %>`.  
  
    -   XML-Elementliteral.  
  
    -   XML-Kommentarliteral. Finden Sie unter [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).  
  
    -   XML-Verarbeitungsanweisungsliteral. Finden Sie unter [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).  
  
    -   XML CDATA-literal. Finden Sie unter [XML-CDATA-Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).  
  
-   `</[name]>`  
  
     Dies ist optional. Stellt das Endtag für das Element an. Das optionale `name` Parameter ist nicht zulässig, wenn es sich um das Ergebnis eines eingebetteten Ausdrucks ist.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XElement>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Sie können mit der Syntax des XML-Elementliterals erstellen <xref:System.Xml.Linq.XElement> Objekte in Ihrem Code.  
  
> [!NOTE]
>  Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen verwenden. Dieser Funktion können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in eine [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Programm.  
  
 Eingebettete Ausdrücke des Formulars `<%= exp %>` ermöglichen es Ihnen, einem XML-Elementliteral dynamische Informationen hinzugefügt. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler konvertiert das XML-Elementliteral in Aufrufe an die <xref:System.Xml.Linq.XElement.%23ctor%2A> Konstruktor und, falls erforderlich, die <xref:System.Xml.Linq.XAttribute.%23ctor%2A> Konstruktor.  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 XML-Namespacepräfixe sind nützlich, wenn Sie XML-Literale mit Elementen aus dem gleichen Namespace oft im Code zu erstellen. Können Sie globale XML-Namespacepräfixe verwenden, die Sie definieren, mit der `Imports` -Anweisung oder lokale Präfixe, die Sie definieren, mit der `xmlns:xmlPrefix="xmlNamespace"` Attributsyntax. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
 Gemäß den Bereichsregeln für XML-Namespaces haben lokale Präfixe Vorrang vor globalen Präfixen. Wenn ein XML-Literal einen XML-Namespace definiert, ist dieser Namespace nicht verfügbar für Ausdrücke, die in einem eingebetteten Ausdruck angezeigt werden. Die eingebettete Ausdruck kann nur die globalen XML-Namespace zugreifen.  
  
 Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler konvertiert jedes globale XML-Namespace, die von einem XML-literal in eine lokale Namespacedefinition im generierten Code verwendet wird. Globale XML-Namespaces, die nicht verwendet werden, erscheinen nicht im generierten Code.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie ein einfaches XML-Element erstellt, die zwei geschachtelte leere Elemente.  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 Das Beispiel zeigt den folgenden Text an. Beachten Sie, dass das Literal, die Struktur der leeren Elemente beibehält.  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie mit eingebetteten Ausdrücken erstellen Attribute und benennen ein Element.  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Klicken Sie dann das Präfix des Namespace zum Erstellen von XML-literal verwendet, und zeigt die endgültige Form des Elements an.  
  
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
  
 Beachten Sie, dass der Compiler das Präfix des globalen XML-Namespace in eine Präfixdefinition für den XML-Namespace konvertiert. Die \<Ns:middle >-Element definiert das XML-Namespacepräfix für die \<Ns:inner1 > Element. Allerdings die \<Ns:inner2 >-Element verwendet den Namespace definiert, durch die `Imports` Anweisung.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>  
 [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [XML-CDATA-Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)  
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
