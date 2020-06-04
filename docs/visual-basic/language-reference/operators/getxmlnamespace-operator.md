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
ms.openlocfilehash: 85422fb9e11d78e228577adc25cba746149c645a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371115"
---
# <a name="getxmlnamespace-operator-visual-basic"></a>GetXmlNamespace-Operator (Visual Basic)
Ruft das- <xref:System.Xml.Linq.XNamespace> Objekt ab, das dem angegebenen XML-Namespace Präfix entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Bestandteile  
 `xmlNamespacePrefix`  
 Optional. Die Zeichenfolge, die das XML-Namespace Präfix identifiziert. Wenn angegeben, muss diese Zeichenfolge ein gültiger XML-Bezeichner sein. Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Wenn kein Präfix angegeben wird, wird der Standard Namespace zurückgegeben. Wenn kein Standard Namespace angegeben wird, wird der leere Namespace zurückgegeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Das- <xref:System.Xml.Linq.XNamespace> Objekt, das dem XML-Namespace Präfix entspricht.  
  
## <a name="remarks"></a>Bemerkungen  
 Der- `GetXmlNamespace` Operator Ruft das-Objekt ab <xref:System.Xml.Linq.XNamespace> , das dem XML-Namespace Präfix entspricht `xmlNamespacePrefix` .  
  
 Sie können XML-Namespace Präfixe direkt in XML-Literalen und XML-Achsen Eigenschaften verwenden. Allerdings müssen Sie den- `GetXmlNamespace` Operator verwenden, um ein Namespace Präfix in ein Objekt zu konvertieren, <xref:System.Xml.Linq.XNamespace> bevor Sie es in Ihrem Code verwenden können. Sie können einen nicht qualifizierten Elementnamen an ein Objekt anfügen, <xref:System.Xml.Linq.XNamespace> um ein voll qualifizierter Objekt zu erhalten <xref:System.Xml.Linq.XName> , das viele [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Methoden erfordert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird `ns` als XML-Namespace Präfix importiert. Anschließend wird das Präfix des-Namespace verwendet, um ein XML-Literalelement zu erstellen und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen zuzugreifen `ns:phone` . Er übergibt dann diesen untergeordneten Knoten an die `ShowName` Unterroutine, die mithilfe des-Operators einen qualifizierten Namen erstellt `GetXmlNamespace` . Die `ShowName` Unterroutine übergibt dann den qualifizierten Namen an die- <xref:System.Xml.Linq.XNode.Ancestors%2A> Methode, um den übergeordneten Knoten zu erhalten `ns:contact` .  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 Wenn Sie den Befehl ausführen `TestGetXmlNamespace.RunSample()` , wird ein Meldungs Feld angezeigt, das den folgenden Text enthält:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Weitere Informationen

- [Imports-Anweisung (XML-Namespace)](../statements/imports-statement-xml-namespace.md)
- [Zugreifen auf XML in Visual Basic](../../programming-guide/language-features/xml/accessing-xml.md)
