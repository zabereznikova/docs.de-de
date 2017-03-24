---
title: Untergeordnete XML-Achseneigenschaft (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyChildAxis
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
caps.latest.revision: 18
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
ms.openlocfilehash: 97b92f9e94ad709c4d8ce944577eb23edc84b328
ms.lasthandoff: 03/13/2017

---
# <a name="xml-child-axis-property-visual-basic"></a>Untergeordnete XML-Achseneigenschaft (Visual Basic)
Bietet Zugriff auf die untergeordneten Elemente eines der folgenden: ein <xref:System.Xml.Linq.XElement>-Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, das eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte oder eine Auflistung von <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
## <a name="syntax"></a>Syntax  
  
```  
  
object.<child>  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`object`|Erforderlich. Ein <xref:System.Xml.Linq.XElement>-Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, das eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte oder eine Auflistung von <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>|  
|.<|Erforderlich. Gibt den Anfang einer untergeordneten Achseneigenschaft an.|  
|`child`|Erforderlich. Name der untergeordneten Knoten des Formulars Zugriff auf [`prefix``:`]`name`.<br /><br /> -   `Prefix`-Dies ist optional. XML-Namespacepräfix für den untergeordneten Knoten. Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.<br />-   `Name`-Erforderlich. Lokaler Name des untergeordneten Knotens. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
|>|Erforderlich. Gibt das Ende einer untergeordneten Achseneigenschaft an.|  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement>  
  
## <a name="remarks"></a>Hinweise  
 Können Sie eine untergeordnete XML-Achseneigenschaft Zugriff auf untergeordnete Knoten anhand des Namens von einer <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>-Objekt, oder aus einer Auflistung von <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Verwenden Sie die XML-`Value`-Eigenschaft, um auf den Wert des ersten untergeordneten Knotens in der zurückgegebenen Auflistung zuzugreifen. Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert die untergeordneten Achseneigenschaften in Aufrufe an die <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode.</xref:System.Xml.Linq.XContainer.Elements%2A>  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Für den Namen in einer untergeordneten Achseneigenschaft können nur XML-Namespacepräfixe verwendet werden, die mit der `Imports`-Anweisung global deklariert wurden. Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie auf die untergeordneten Knoten mit dem Namen `phone` aus dem `contact`-Objekt zugegriffen werden kann.  
  
 [!code-vb[VbXMLSamples&17;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dargestellt, wie auf die untergeordneten Knoten mit dem Namen `phone` aus der Auflistung zugegriffen werden kann, die von der untergeordneten `contact`-Achseneigenschaft des `contacts`-Objekts zurückgegeben wurde.  
  
 [!code-vb[VbXMLSamples&18;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.  
  
 [!code-vb[VbXMLSamples Nr.&19;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>   
 [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
