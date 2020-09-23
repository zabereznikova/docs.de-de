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
ms.openlocfilehash: 8ffe6d5ed368aee6d6984ec6ab28c8832921a3f8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080178"
---
# <a name="accessing-xml-in-visual-basic"></a>Zugreifen auf XML in Visual Basic

Visual Basic stellt XML-Achsen Eigenschaften zum Zugreifen auf und Navigieren in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Strukturen bereit. Diese Eigenschaften verwenden eine spezielle Syntax, damit Sie auf Elemente und Attribute zugreifen können, indem Sie die XML-Namen angeben.  
  
 In der folgenden Tabelle sind die sprach Features aufgelistet, die Ihnen den Zugriff auf XML-Elemente und-Attribute in Visual Basic ermöglichen.  
  
### <a name="xml-axis-properties"></a>XML-Achseneigenschaften  
  
|Beschreibung der Eigenschaft|Beispiel|Beschreibung|  
|--------------------------|-------------|-----------------|  
|*Untergeordnete Achse*|`contact.<phone>`|Ruft alle- `phone` Elemente ab, die untergeordnete Elemente des- `contact` Elements sind.|  
|*Attributachse*|`phone.@type`|Ruft alle `type` Attribute des `phone` Elements ab.|  
|*descendant-Achse*|`contacts...<name>`|Ruft alle `name` Elemente des- `contacts` Elements ab, unabhängig davon, wie tief Sie in der Hierarchie vorkommen.|  
|*Erweiterungsindexer*|`contacts...<name>(0)`|Ruft das erste `name` Element aus der Sequenz ab.|  
|*value*|`contacts...<name>.Value`|Ruft die Zeichen folgen Darstellung des ersten Objekts in der Sequenz ab, oder, `Nothing` Wenn die Sequenz leer ist.|  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Vorgehensweise: Zugreifen auf XML-Nachfolgerelemente](how-to-access-xml-descendant-elements.md)  
 Zeigt, wie Sie mithilfe einer untergeordneten Achsen Eigenschaft auf alle XML-Elemente zugreifen, die einen angegebenen Namen aufweisen und die unter einem angegebenen XML-Element enthalten sind.  
  
 [Vorgehensweise: Zugreifen auf untergeordnete XML-Elemente](how-to-access-xml-child-elements.md)  
 Zeigt, wie Sie mit einer untergeordneten Achsen Eigenschaft auf alle untergeordneten XML-Elemente zugreifen, die einen angegebenen Namen in einem XML-Element aufweisen.  
  
 [Vorgehensweise: Zugreifen auf XML-Attribute](how-to-access-xml-attributes.md)  
 Zeigt, wie eine Attribut Achsen Eigenschaft für den Zugriff auf alle XML-Attribute mit einem angegebenen Namen in einem XML-Element verwendet wird.  
  
 [Vorgehensweise: Deklarieren und Verwenden von XML-Namespacepräfixen](how-to-declare-and-use-xml-namespace-prefixes.md)  
 Zeigt, wie ein XML-Namespace Präfix deklariert und zum Erstellen und Zugreifen auf XML-Elemente verwendet wird.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [XML-Achseneigenschaften](../../../language-reference/xml-axis/index.md)  
 Enthält Links zu Abschnitten, in denen die verschiedenen XML-Zugriffs Eigenschaften beschrieben werden.  
  
 [Übersicht über LINQ to XML in Visual Basic](overview-of-linq-to-xml.md)  
 Bietet eine Einführung in die Verwendung von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.  
  
 [Erstellen von XML in Visual Basic](creating-xml.md)  
 Bietet eine Einführung in die Verwendung von XML-Literalen in Visual Basic.  
  
 [Bearbeiten von XML in Visual Basic](manipulating-xml.md)  
 Enthält Links zu Abschnitten über das Laden und Ändern von XML in Visual Basic.  
  
 [XML](index.md)  
 Enthält Links zu Abschnitten, in denen die Verwendung von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic beschrieben wird.
