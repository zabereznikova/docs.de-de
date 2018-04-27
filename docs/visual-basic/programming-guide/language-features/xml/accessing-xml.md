---
title: Zugreifen auf XML in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
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
ms.openlocfilehash: 064e4b224d37172b8f79e57c73164b90186ef922
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="accessing-xml-in-visual-basic"></a>Zugreifen auf XML in Visual Basic
Visual Basic bietet XML-Achseneigenschaften für den Zugriff auf und die berichtsnavigation [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Strukturen. Diese Eigenschaften verwenden eine spezielle Syntax, um die Elemente und Attribute zugreifen, indem Sie die XML-Namen angeben können.  
  
 Die folgende Tabelle enthält die Sprachfunktionen, die Ihnen den Zugriff auf XML-Elemente und Attribute in Visual Basic ermöglichen.  
  
### <a name="xml-axis-properties"></a>XML-Achseneigenschaften  
  
|Beschreibung der Eigenschaft|Beispiel|Beschreibung|  
|--------------------------|-------------|-----------------|  
|*Child-Achse*|`contact.<phone>`|Ruft alle `phone` Elemente, die untergeordneten Elemente sind die `contact` Element.|  
|*Attribute-Achse*|`phone.@type`|Ruft alle `type` Attribute der `phone` Element.|  
|*descendant-Achse*|`contacts...<name>`|Ruft alle `name` Elemente der `contacts` Element, unabhängig davon, wie tief in der Hierarchie, die sie auftreten.|  
|*erweiterungsindizierer*|`contacts...<name>(0)`|Ruft das erste `name` Element aus der Sequenz.|  
|*Wert*|`contacts...<name>.Value`|Ruft eine Zeichenfolgendarstellung des ersten Objekts in der Sequenz oder `Nothing` , wenn die Sequenz leer ist.|  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Zugreifen auf XML-Nachfolgerelemente](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Zeigt, wie eine descendant-Achse-Eigenschaft verwenden, um Zugriff auf alle XML-Elemente, die einen angegebenen Namen aufweisen und unter einem angegebenen XML-Element enthalten sind.  
  
 [Gewusst wie: Zugreifen auf untergeordnete XML-Elemente](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Zeigt, wie einer untergeordneten Achseneigenschaft auf alle untergeordnete XML-Elemente, die den angegebenen Namen in ein XML-Element aufweisen.  
  
 [Gewusst wie: Zugreifen auf XML-Attribute](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Zeigt, wie eine Attributachseneigenschaft zu verwenden, um alle XML-Attribute zuzugreifen, die einen angegebenen Namen in ein XML-Element aufweisen.  
  
 [Gewusst wie: Deklarieren und Verwenden von XML-Namespacepräfixen](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Zeigt, wie ein XML-Namespacepräfix zu deklarieren und verwenden sie zum Erstellen und Zugriff auf XML-Elemente.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [XML-Achseneigenschaften](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 Enthält Links zu Abschnitten, beschreibt die verschiedenen Eigenschaften der XML-Zugriff.  
  
 [Übersicht über LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Bietet eine Einführung zur Verwendung [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.  
  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Bietet eine Einführung in die Verwendung von XML-Literalen in Visual Basic.  
  
 [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Enthält Links zu Abschnitten zum Laden und Ändern von XML in Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Enthält Links zu Abschnitten, die beschreiben, wie mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.
