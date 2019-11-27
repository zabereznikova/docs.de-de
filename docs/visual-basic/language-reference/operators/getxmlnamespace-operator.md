---
title: GetXmlNamespace-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 4d6e738f4e3a47d73e37c395dd74fe19e99d81bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353189"
---
# <a name="getxmlnamespace-operator-visual-basic"></a>GetXmlNamespace-Operator (Visual Basic)
Ruft das <xref:System.Xml.Linq.XNamespace>-Objekt ab, das dem angegebenen XML-Namespace Präfix entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>-Komponenten  
 `xmlNamespacePrefix`  
 Optional. Die Zeichenfolge, die das XML-Namespace Präfix identifiziert. Wenn angegeben, muss diese Zeichenfolge ein gültiger XML-Bezeichner sein. Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Wenn kein Präfix angegeben wird, wird der Standard Namespace zurückgegeben. Wenn kein Standard Namespace angegeben wird, wird der leere Namespace zurückgegeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Das <xref:System.Xml.Linq.XNamespace>-Objekt, das dem XML-Namespace Präfix entspricht.  
  
## <a name="remarks"></a>Hinweise  
 Der `GetXmlNamespace`-Operator Ruft das <xref:System.Xml.Linq.XNamespace> Objekt ab, das dem XML-Namespace Präfix `xmlNamespacePrefix`entspricht.  
  
 Sie können XML-Namespace Präfixe direkt in XML-Literalen und XML-Achsen Eigenschaften verwenden. Allerdings müssen Sie den `GetXmlNamespace`-Operator verwenden, um ein Namespace Präfix in ein <xref:System.Xml.Linq.XNamespace> Objekt zu konvertieren, bevor Sie es in Ihrem Code verwenden können. Sie können einen nicht qualifizierten Elementnamen an ein <xref:System.Xml.Linq.XNamespace> Objekt anfügen, um ein voll qualifizierter <xref:System.Xml.Linq.XName> Objekt zu erhalten, das viele [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Methoden erfordert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird `ns` als XML-Namespace Präfix importiert. Anschließend wird das Präfix des-Namespace verwendet, um ein XML-Literalelement zu erstellen und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:phone`zuzugreifen. Er übergibt dann diesen untergeordneten Knoten an die `ShowName` Unterroutine, die mithilfe des `GetXmlNamespace`-Operators einen qualifizierten Namen erstellt. Die `ShowName` Unterroutine übergibt dann den qualifizierten Namen an die <xref:System.Xml.Linq.XNode.Ancestors%2A>-Methode, um den übergeordneten `ns:contact` Knoten zu erhalten.  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 Wenn Sie `TestGetXmlNamespace.RunSample()`aufgerufen wird, wird ein Meldungs Feld angezeigt, das den folgenden Text enthält:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Siehe auch

- [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [Zugreifen auf XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
