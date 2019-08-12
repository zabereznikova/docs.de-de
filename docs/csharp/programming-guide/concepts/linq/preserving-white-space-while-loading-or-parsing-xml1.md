---
title: Beibehalten von Leerzeichen beim Laden oder Parsen von XML
ms.date: 07/20/2015
ms.assetid: f3ff58c4-55aa-4fcd-b933-e3a2ee6e706c
ms.openlocfilehash: 263121468b3010884c14c9e593a857d01dc253ef
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68868819"
---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Beibehalten von Leerzeichen beim Laden oder Parsen von XML
In diesem Thema wird beschrieben, wie das Leerraumverhalten von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] gesteuert werden kann.  
  
 Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert. Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten. Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert. Sie möchten nicht, dass diese Einzüge irgendwie geändert werden. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.  
  
 In diesem Thema wird das Leerraumverhalten von Methoden beschrieben, die XML-Strukturen auffüllen. Informationen zum Steuern des Leerraumverhaltens beim Serialisieren von XML-Strukturen finden Sie unter [Beibehalten von Leerzeichen beim Serialisieren](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Verhalten von Methoden, die XML-Strukturen auffüllen  
 Die folgenden Methoden in den Klassen <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XDocument> füllen eine XML-Struktur auf. Sie können eine XML-Struktur von einer Datei, einem <xref:System.IO.TextReader>, einem <xref:System.Xml.XmlReader> oder einer Zeichenfolge aus auffüllen:  
  
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
  
 Wenn die Methode nicht <xref:System.Xml.Linq.LoadOptions> als Argument akzeptiert, bleibt nicht signifikanter Leerraum nicht erhalten.  
  
 In den meisten Fällen können Sie nicht signifikanten Leerraum optional als Textknoten in der XML-Struktur erhalten, sofern die Methode <xref:System.Xml.Linq.LoadOptions> als Argument akzeptiert. Wenn die Methode den XML-Code aber aus einem <xref:System.Xml.XmlReader> lädt, bestimmt dieser <xref:System.Xml.XmlReader> ob Leerraum beibehalten wird. Die Einrichtung von <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> hat keine Auswirkungen.  
  
 Bei diesen Methoden wird nicht signifikanter Leerraum als <xref:System.Xml.Linq.XText>-Knoten in die XML-Struktur eingefügt, sofern Leerraum beibehalten wird. Wenn Leerraum nicht beibehalten wird, erfolgt keine Einfügung von Textknoten.  
  
 Zum Erstellen einer XML-Struktur können Sie einen <xref:System.Xml.XmlWriter> verwenden. Knoten, die in den <xref:System.Xml.XmlWriter> geschrieben werden, werden in der Struktur aufgefüllt. Wenn Sie jedoch eine XML-Struktur mit dieser Methode erstellen, bleiben alle Knoten unabhängig davon erhalten, ob der Knoten Leerraum ist und ob er signifikant ist.  
  