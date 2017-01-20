---
title: "Accessing XML in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "LINQ to XML [Visual Basic], accessing XML"
  - "Visual Basic code, XML"
  - "accessing XML [Visual Basic], axis properties"
  - "XML [Visual Basic], axis properties"
  - "XML [Visual Basic], accessing"
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Accessing XML in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mit den XML\-Achseneigenschaften von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] kann auf [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]\-Strukturen zugegriffen und darin navigiert werden.  Diese Eigenschaften verwenden eine spezielle Syntax, um den Zugriff auf Elemente und Attribute durch Angabe von XML\-Namen zu ermöglichen.  
  
 Die folgende Tabelle listet die Sprachfeatures auf, mit denen auf XML\-Elemente und \-Attribute in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] zugegriffen werden kann.  
  
### XML\-Achseneigenschaften  
  
|Eigenschaftenbeschreibung|Beispiel|Beschreibung|  
|-------------------------------|--------------|------------------|  
|*Untergeordnete Achse*|`contact.<phone>`|Ruft alle `phone`\-Elemente ab, die untergeordnete Elemente des `contact`\-Elements sind.|  
|*Attributachse*|`phone.@type`|Ruft alle `type`\-Attribute des `phone`\-Elements ab.|  
|*Nachfolgerachse*|`contacts...<name>`|Ruft alle `name`\-Elemente des `contacts`\-Elements ab, unabhängig davon, wie tief sie in der Hierarchieebene liegen.|  
|*Erweiterungsindexer*|`contacts...<name>(0)`|Ruft das erste `name`\-Element der Sequenz ab.|  
|*value*|`contacts...<name>.Value`|Ruft die Zeichenfolgendarstellung des ersten Objekts in der Sequenz oder `Nothing` ab, wenn die Sequenz leer ist.|  
  
## In diesem Abschnitt  
 [How to: Access XML Descendant Elements](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Zeigt, wie mit einer Nachfolgerachseneigenschaft auf alle XML\-Elemente zugegriffen werden kann, die einen bestimmten Namen haben und die einem bestimmten XML\-Element untergeordnet sind.  
  
 [How to: Access XML Child Elements](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Zeigt, wie eine untergeordnete Achseneigenschaft verwendet wird, um auf alle untergeordneten XML\-Elemente zuzugreifen, die einen bestimmten Namen in einem XML\-Element haben.  
  
 [How to: Access XML Attributes](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Zeigt, wie ein Achseneigenschaftattribut verwendet wird, um auf alle XML\-Attribute zuzugreifen, die einen bestimmten Namen in einem XML\-Element haben.  
  
 [How to: Declare and Use XML Namespace Prefixes](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Zeigt, wie ein XML\-Namespacepräfix deklariert wird und wie damit XML\-Elemente erstellt werden und auf diese zugegriffen wird.  
  
## Verwandte Abschnitte  
 [XML Axis Properties](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 Stellt Links auf Abschnitte bereit, in denen die verschiedenen XML\-Zugriffseigenschaften beschrieben werden.  
  
 [Overview of LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Bietet eine Einführung in die Verwendung von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] in Visual Basic.  
  
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Bietet eine Einführung in die Verwendung von XML\-Literalen in Visual Basic.  
  
 [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Stellt Links zu Abschnitten bereit, in den das Laden und Ändern von XML in Visual Basic beschrieben wird.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Stellt Links zu Abschnitten bereit, in denen die Verwendung von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] in Visual Basic beschrieben wird.