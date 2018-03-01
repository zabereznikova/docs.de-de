---
title: XML-Nachfolgerachseneigenschaft (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f3c42b5134b058c010ca4c7a5ee7c24627c65fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xml-descendant-axis-property-visual-basic"></a>XML-Nachfolgerachseneigenschaft (Visual Basic)
Bietet Zugriff auf die Nachfolger: ein <xref:System.Xml.Linq.XElement> -Objekt, ein <xref:System.Xml.Linq.XDocument> -Objekt, das eine Auflistung von <xref:System.Xml.Linq.XElement> Objekte oder eine Auflistung von <xref:System.Xml.Linq.XDocument> Objekte.  
  
## <a name="syntax"></a>Syntax  
  
```  
object...<descendant>  
```  
  
## <a name="parts"></a>Teile  
 `object`  
 Erforderlich. Ein <xref:System.Xml.Linq.XElement>Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, eine Auflistung von <xref:System.Xml.Linq.XElement>Objekten oder eine Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.  
  
 ...<  
 Erforderlich. Kennzeichnet den Anfang einer untergeordneten Achseneigenschaft an.  
  
 `descendant`  
 Erforderlich. Name der untergeordneten Knoten des Formulars den Zugriff auf [`prefix``:`]`name`.  
  
|Segment|Beschreibung|  
|----------|-----------------|  
|`prefix`|Dies ist optional. XML-Namespacepräfix für den untergeordneten Knoten. Muss ein globaler XML-Namespace, die mithilfe von definiert ist ein `Imports` Anweisung.|  
|`name`|Erforderlich. Lokale Name des untergeordneten Knotens. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Erforderlich. Kennzeichnet das Ende einer untergeordneten Achseneigenschaft an.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine XML-Achseneigenschaft Nachfolgerknoten anhand des Namens aus den Zugriff auf eine <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> -Objekt, oder aus einer Auflistung von <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekte. Mit dem XML- `Value` Eigenschaft, um den Wert des ersten untergeordneten Knotens in der zurückgegebenen Auflistung zuzugreifen. Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler konvertiert die untergeordneten Achseneigenschaften in Aufrufe der <xref:System.Xml.Linq.XContainer.Descendants%2A> Methode.  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Der Name in einer untergeordneten Achseneigenschaft können nur XML-Namespaces, die global deklariert, mit der `Imports` Anweisung. Es können keine XML-Namespaces, die lokal in XML-Elementliteralen deklariert werden. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie Zugriff auf den Wert des ersten untergeordneten Knotens mit dem Namen `name` und die Werte aller Nachfolgerknoten namens `phone` aus der `contacts` Objekt.  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Es verwendet dann das Namespacepräfix ein XML-literal erstellt und auf den Wert des ersten untergeordneten Knotens mit dem qualifizierten Namen zugreifen `ns:name`.  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>  
 [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
