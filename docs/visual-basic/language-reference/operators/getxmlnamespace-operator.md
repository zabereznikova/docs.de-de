---
title: GetXmlNamespace-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47ba67bc58debf8f144f6468bf510932414c0698
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="getxmlnamespace-operator-visual-basic"></a>GetXmlNamespace-Operator (Visual Basic)
Ruft die <xref:System.Xml.Linq.XNamespace> Objekt, das das angegebene XML-Namespacepräfix entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Teile  
 `xmlNamespacePrefix`  
 Dies ist optional. Die Zeichenfolge, die das XML-Namespacepräfix identifiziert. Wenn angegeben, muss diese Zeichenfolge ein gültiger XML-Bezeichner. Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Wenn kein Präfix angegeben ist, wird der Standardnamespace zurückgegeben. Wenn kein Standardnamespace angegeben ist, wird der leere Namespace zurückgegeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Die <xref:System.Xml.Linq.XNamespace> Objekt, das das XML-Namespacepräfix entspricht.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetXmlNamespace` Operator Ruft die <xref:System.Xml.Linq.XNamespace> Objekt, das das XML-Namespacepräfix entspricht `xmlNamespacePrefix`.  
  
 Sie können XML-Namespacepräfixe direkt im XML-Literale und XML-Achseneigenschaften verwenden. Allerdings müssen Sie mithilfe der `GetXmlNamespace` Operator, um ein Namespacepräfix zu konvertieren einer <xref:System.Xml.Linq.XNamespace> Objekt, bevor Sie es in Ihrem Code verwenden können. Können Sie einen nicht qualifizierten Elementnamen zum Anfügen einer <xref:System.Xml.Linq.XNamespace> einen vollqualifizierten abzurufenden Objekts <xref:System.Xml.Linq.XName> -Objekt, das für viele [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Methoden erfordern.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird importiert `ns` als ein XML-Namespacepräfix. Es verwendet dann das Namespacepräfix ein XML-literal erstellt und Zugriff auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:phone`. Es übergibt dann diese untergeordneten Knoten, der die `ShowName` -Unterroutine, die mit einen qualifizierten Namen erstellt die `GetXmlNamespace` Operator. Die `ShowName` Unterroutine übergibt dann den qualifizierten Namen an die <xref:System.Xml.Linq.XNode.Ancestors%2A> Methode zum Abrufen der übergeordneten `ns:contact` Knoten.  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 Beim Aufruf `TestGetXmlNamespace.RunSample()`, es wird ein Meldungsfeld mit dem folgenden Text angezeigt:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Siehe auch  
 [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [Zugreifen auf XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
