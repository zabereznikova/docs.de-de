---
title: Aufrufen von XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 1fa1d94fc710272ac0ba9ea7167989da42a51fcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351745"
---
# <a name="accessing-xml-in-visual-basic"></a>Zugreifen auf XML in Visual Basic
Visual Basic stellt XML-Achsen Eigenschaften für den Zugriff und die Navigation [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Strukturen bereit. Diese Eigenschaften verwenden eine spezielle Syntax, damit Sie auf Elemente und Attribute zugreifen können, indem Sie die XML-Namen angeben.  
  
 In der folgenden Tabelle sind die sprach Features aufgelistet, die Ihnen den Zugriff auf XML-Elemente und-Attribute in Visual Basic ermöglichen.  
  
### <a name="xml-axis-properties"></a>XML-Achseneigenschaften  
  
|Eigenschafts Beschreibung|Beispiel|Beschreibung|  
|--------------------------|-------------|-----------------|  
|*Untergeordnete Achse*|`contact.<phone>`|Ruft alle `phone` Elemente ab, die untergeordnete Elemente des `contact`-Elements sind.|  
|*Attribut Achse*|`phone.@type`|Ruft alle `type` Attribute des `phone` Elements ab.|  
|*Nachfolger Achse*|`contacts...<name>`|Ruft alle `name` Elemente des `contacts` Elements ab, unabhängig davon, wie tief Sie in der Hierarchie vorkommen.|  
|*Erweiterungsindexer*|`contacts...<name>(0)`|Ruft das erste `name`-Element aus der Sequenz ab.|  
|*Wert*|`contacts...<name>.Value`|Ruft die Zeichen folgen Darstellung des ersten Objekts in der Sequenz ab oder `Nothing`, wenn die Sequenz leer ist.|  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Zugreifen auf XML-Nachfolgerelemente](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Zeigt, wie Sie mithilfe einer untergeordneten Achsen Eigenschaft auf alle XML-Elemente zugreifen, die einen angegebenen Namen aufweisen und die unter einem angegebenen XML-Element enthalten sind.  
  
 [Gewusst wie: Zugreifen auf untergeordnete XML-Elemente](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Zeigt, wie Sie mit einer untergeordneten Achsen Eigenschaft auf alle untergeordneten XML-Elemente zugreifen, die einen angegebenen Namen in einem XML-Element aufweisen.  
  
 [Gewusst wie: Zugreifen auf XML-Attribute](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Zeigt, wie eine Attribut Achsen Eigenschaft für den Zugriff auf alle XML-Attribute mit einem angegebenen Namen in einem XML-Element verwendet wird.  
  
 [Gewusst wie: Deklarieren und Verwenden von XML-Namespacepräfixen](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Zeigt, wie ein XML-Namespace Präfix deklariert und zum Erstellen und Zugreifen auf XML-Elemente verwendet wird.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [XML-Achseneigenschaften](../../../../visual-basic/language-reference/xml-axis/index.md)  
 Enthält Links zu Abschnitten, in denen die verschiedenen XML-Zugriffs Eigenschaften beschrieben werden.  
  
 [Übersicht über LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Bietet eine Einführung in die Verwendung von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.  
  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Bietet eine Einführung in die Verwendung von XML-Literalen in Visual Basic.  
  
 [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Enthält Links zu Abschnitten über das Laden und Ändern von XML in Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Enthält Links zu Abschnitten, in denen beschrieben wird, wie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic verwendet wird.
