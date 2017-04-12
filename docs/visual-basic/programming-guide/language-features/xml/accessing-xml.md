---
title: Zugreifen auf XML in Visual Basic | Microsoft-Dokumentation
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
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 215f057f0b4d884369aad53cbbdbb98f240b56c4
ms.lasthandoff: 03/13/2017

---
# <a name="accessing-xml-in-visual-basic"></a>Zugreifen auf XML in Visual Basic
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]zum Zugreifen auf und Navigieren in XML-Achseneigenschaften kann [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Strukturen. Diese Eigenschaften verwenden eine spezielle Syntax, um die Elemente und Attribute zugreifen, indem die XML-Namen angeben können.  
  
 Die folgende Tabelle listet die Sprachfeatures, mit denen Sie Zugriff auf XML-Elemente und Attribute in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### <a name="xml-axis-properties"></a>XML-Achseneigenschaften  
  
|Beschreibung der Eigenschaft|Beispiel|Beschreibung|  
|--------------------------|-------------|-----------------|  
|*Child-Achse*|`contact.<phone>`|Ruft alle `phone` Elemente, die untergeordnete Elemente von sind die `contact` Element.|  
|*Attribute-Achse*|`phone.@type`|Ruft alle `type` Attribute der `phone` Element.|  
|*descendant-Achse*|`contacts...<name>`|Ruft alle `name` Elemente der `contacts` Element, unabhängig davon, wie viele Ebenen in der Hierarchie, die sie auftreten.|  
|*erweiterungsindizierer*|`contacts...<name>(0)`|Ruft die erste `name` Element aus der Sequenz.|  
|*value*|`contacts...<name>.Value`|Ruft die Darstellung des ersten Objekts in der Sequenz oder `Nothing` , wenn die Sequenz leer ist.|  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Zugreifen auf XML-Nachfolgerelemente](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Veranschaulicht, wie einen Nachfolger-Achseneigenschaft auf alle XML-Elemente, die einen angegebenen Namen aufweisen und unter einem angegebenen XML-Element enthalten sind.  
  
 [Gewusst wie: Zugreifen auf untergeordnete XML-Elemente](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Veranschaulicht, wie eine untergeordnete Achseneigenschaft auf alle untergeordneten XML-Elemente zuzugreifen, die in einem XML-Element angegebenen Namen aufweisen.  
  
 [Gewusst wie: Zugreifen auf XML-Attribute](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Veranschaulicht, wie eine Attributachseneigenschaft auf alle XML-Attribute zuzugreifen, die in einem XML-Element angegebenen Namen aufweisen.  
  
 [Gewusst wie: Deklarieren und Verwenden von XML-Namespacepräfixen](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Zeigt, wie ein XML-Namespacepräfix deklariert und zum Erstellen und Zugreifen auf XML-Elemente.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [XML-Achseneigenschaften](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 Enthält Links zu Abschnitten beschreiben die verschiedenen XML-Zugriffseigenschaften.  
  
 [Übersicht über LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Bietet eine Einführung zur Verwendung [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.  
  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Bietet eine Einführung zur Verwendung von XML-Literalen in Visual Basic.  
  
 [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Enthält Links zu Abschnitten zum Laden und Ändern von XML in Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Enthält Links zu Abschnitten, die zur Verwendung [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.
