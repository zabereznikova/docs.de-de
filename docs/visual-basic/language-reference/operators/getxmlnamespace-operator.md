---
title: GetXmlNamespace-Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
dev_langs:
- VB
helpviewer_keywords:
- GetXmlNamespace operator
- GetXmlNamespace keyword
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: 14
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
ms.openlocfilehash: 929ba4edae9e155245228670424a3898896da807
ms.lasthandoff: 03/13/2017

---
# <a name="getxmlnamespace-operator-visual-basic"></a>GetXmlNamespace-Operator (Visual Basic)
Ruft die <xref:System.Xml.Linq.XNamespace>Objekt, das dem angegebenen XML-Namespacepräfix entspricht.</xref:System.Xml.Linq.XNamespace>  
  
## <a name="syntax"></a>Syntax  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Teile  
 `xmlNamespacePrefix`  
 Optional. Die Zeichenfolge, die das XML-Namespacepräfix identifiziert. Wenn angegeben, muss diese Zeichenfolge ein gültiger XML-Bezeichner sein. Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Wenn kein Präfix angegeben ist, wird der Standardnamespace zurückgegeben. Wenn kein Standardnamespace angegeben ist, wird der leere Namespace zurückgegeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Das <xref:System.Xml.Linq.XNamespace>Objekt, das das XML-Namespacepräfix entspricht.</xref:System.Xml.Linq.XNamespace>  
  
## <a name="remarks"></a>Hinweise  
 Die `GetXmlNamespace` Operator Ruft das <xref:System.Xml.Linq.XNamespace>Objekt, das das XML-Namespacepräfix entspricht `xmlNamespacePrefix`.</xref:System.Xml.Linq.XNamespace>  
  
 Sie können XML-Namespacepräfixe direkt in XML-Literale und XML-Achseneigenschaften verwenden. Allerdings müssen Sie verwenden die `GetXmlNamespace` Operator, um ein Namespacepräfix konvertieren ein <xref:System.Xml.Linq.XNamespace>Objekt, bevor Sie es in Ihrem Code verwenden können.</xref:System.Xml.Linq.XNamespace> Können Sie einen nicht qualifizierten Elementnamen zum Anfügen einer <xref:System.Xml.Linq.XNamespace>-Objekts können Sie einen vollqualifizierten abrufen <xref:System.Xml.Linq.XName>-Objekt, das für viele [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Methoden erfordern.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace>  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel importiert `ns` als ein XML-Namespacepräfix. Anschließend wird mithilfe der Namespacepräfix ein XML-literal erstellt und Zugriff auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:phone`. Anschließend übergibt dieser untergeordnete Knoten an die `ShowName` -Unterroutine, die einen qualifizierten Namen, indem erstellt die `GetXmlNamespace` Operator. Die `ShowName` -Unterroutine übergibt dann den qualifizierten Namen an die <xref:System.Xml.Linq.XNode.Ancestors%2A>Methode zum Abrufen der übergeordneten `ns:contact` Knoten.</xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
 [!code-vb[VbXMLSamples&#38;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 Beim Aufruf von `TestGetXmlNamespace.RunSample()`, es wird ein Meldungsfeld mit dem folgenden Text angezeigt:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Siehe auch  
 [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Zugreifen auf XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
