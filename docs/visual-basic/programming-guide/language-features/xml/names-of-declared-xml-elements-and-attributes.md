---
title: Namen von deklarierten XML-Elementen und Attributen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
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
ms.openlocfilehash: ed8ecf69170acf9745a4038975e7e3421722d52d
ms.lasthandoff: 03/13/2017

---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Namen von deklarierten XML-Elementen und Attributen (Visual Basic)
Dieses Thema enthält [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Richtlinien für die Benennung von XML-Elementen und Attributen in XML-Literalen.  In einem XML-literal können Sie einen lokalen Namen oder einen qualifizierten Namen angeben. Ein qualifizierter Name besteht aus einer XML-Namespacepräfix, einem Doppelpunkt und einem lokalen Namen. Weitere Informationen zu XML-Namespacepräfixen finden Sie unter [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Regeln  
 Einen lokalen Namen eines Elements oder Attributs in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen die folgenden Regeln einhalten.  
  
-   Sie können mit einem Namespace beginnen. Es muss mit einem Buchstaben oder Unterstrich beginnen (`_`).  
  
-   Es darf nur alphabetische Zeichen, Dezimalziffern, Unterstriche, Punkte (.) und Bindestriche (-).  
  
-   Es muss nicht mehr als 1024 Zeichen lang sein.  
  
-   Doppelpunkte, die innerhalb von Namen Namespaceabgrenzungen. Daher können Sie Doppelpunkte nur für einen XML-Namespace für einen bestimmten Namen geben.  
  
 Darüber hinaus sollten Sie sich an die folgenden Richtlinien halten.  
  
-   XML 1.0-Spezifikation reserviert alle Namen, die mit der Zeichenfolge "Xml", der Variation Großschreibung ab. Verwenden Sie daher nicht die Namen für das Element und die Attributnamen.  
  
### <a name="name-length-guidelines"></a>Richtlinien zur Länge von Namen  
 Ein Namen sollten aus praktischen Gründen so kurz wie möglich sein und gleichzeitig die Art des Elements eindeutig kennzeichnen. Dies verbessert die Lesbarkeit des Codes und Länge und die Quelldatei die Größe verringert.  
  
 Ihr Name sollte jedoch nicht so kurz sein, dass es nicht angemessen beantwortet werden, das Element oder wie der Code verwendet. Dies ist wichtig für die Lesbarkeit des Codes. Wenn jemand versucht, zu verstehen, oder wenn Sie sich diese betrachten sehr lange, nachdem Sie ihn geschrieben haben, können geeigneter Elementnamen Zeit sparen.  
  
## <a name="case-sensitivity-in-names"></a>Groß-und Kleinschreibung bei Namen  
 XML-Elementnamen Groß-/Kleinschreibung. Dies bedeutet, dass bei der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler vergleicht zwei Namen, die nur die Groß-und Kleinschreibung unterscheiden, als unterschiedliche Namen interpretiert. Interpretiert z. B. `ABC` und `abc` als Verweise auf verschiedene Elemente.  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Wenn ein XML-Elementliteral erstellen, können Sie das XML-Namespacepräfix für den Elementnamen angeben. Weitere Informationen finden Sie unter [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
