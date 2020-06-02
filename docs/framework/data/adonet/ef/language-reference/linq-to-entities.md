---
title: LINQ to Entities
description: Erfahren Sie, wie Sie LINQ to Entities Abfragen erstellen und ausführen, mit denen Sie mithilfe von Visual Basic oder Visual c# Abfragen für das Entity Framework konzeptionelle Modell schreiben können.
ms.date: 03/30/2017
ms.assetid: 641f9b68-9046-47a1-abb0-1c8eaeda0e2d
ms.openlocfilehash: 389a81872f4652c69e2b845359cf4e5a275aed5c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286843"
---
# <a name="linq-to-entities"></a>LINQ to Entities
LINQ to Entities bietet LINQ (Language Integrated Query)-Unterstützung, die es Entwicklern ermöglicht, in Visual Basic oder Visual C# Abfragen für das konzeptionelle Modell im Entity Framework zu schreiben. Abfragen für das Entity Framework werden als Befehlsstrukturabfragen dargestellt, die für den Objektkontext ausgeführt werden. LINQ to Entities wandelt LINQ (Language-Integrated Queries)-Abfragen in Befehlsstrukturabfragen um, führt die Abfragen für das Entity Framework aus und gibt Objekte zurück, die sowohl vom Entity Framework als auch von LINQ verwendet werden können. Mit folgendem Vorgang können Sie eine LINQ to Entities-Abfrage erstellen und ausführen:  
  
1. Erstellen Sie eine <xref:System.Data.Objects.ObjectQuery%601>-Instanz aus dem <xref:System.Data.Objects.ObjectContext>.  
  
2. Verfassen Sie mithilfe der <xref:System.Data.Objects.ObjectQuery%601>-Instanz eine LINQ to Entities-Abfrage in C# oder Visual Basic.  
  
3. Wandeln Sie LINQ-Standardabfrageoperatoren und -ausdrücke in Befehlsstrukturen um.  
  
4. Führen Sie die als Befehlsstruktur dargestellte Abfrage für die Datenquelle aus. Alle Ausnahmen, die bei der Ausführung für die Datenquelle ausgelöst wurden, werden direkt an den Client weitergegeben.  
  
5. Geben Sie die Abfrageergebnisse an den Client zurück.  
  
## <a name="constructing-an-objectquery-instance"></a>Erstellen einer 'ObjectQuery'-Instanz  
 Die generische <xref:System.Data.Objects.ObjectQuery%601>-Klasse stellt eine Abfrage dar, die eine Auflistung von 0 (null) oder mehr typisierten Entitäten zurückgibt. Eine Objektabfrage wird normalerweise aus einem bestehenden Objektkontext und nicht manuell erstellt. Sie gehört immer zu diesem Objektkontext. Dieser Kontext stellt die Verbindungs- und Metadateninformationen bereit, die zum Verfassen und Ausführen der Abfrage erforderlich sind. Die generische <xref:System.Data.Objects.ObjectQuery%601>-Klasse implementiert die generische <xref:System.Linq.IQueryable%601>-Schnittstelle, durch deren Generatormethoden die inkrementelle Erstellung von LINQ-Abfragen aktiviert wird. Sie können auch den Typ von Entitäten mit dem `var`-Schlüsselwort in C# (`Dim` in Visual Basic, wobei der lokale Typrückschluss aktiviert sein muss) per Rückschluss vom Compiler ableiten lassen.  
  
## <a name="composing-the-queries"></a>Verfassen der Abfragen  
 Instanzen der generischen <xref:System.Data.Objects.ObjectQuery%601>-Klasse, die die generische <xref:System.Linq.IQueryable%601>-Schnittstelle implementiert, dienen als Datenquelle für LINQ to Entities-Abfragen. In einer Abfrage geben Sie genau die Informationen an, die aus der Datenquelle abgerufen werden sollen. In der Abfrage kann auch angegeben werden, wie die Abfrageergebnisse sortiert, gruppiert und formatiert werden sollen, bevor sie zurückgegeben werden. In LINQ wird eine Abfrage in einer Variablen gespeichert. Diese Abfragevariable führt keine Aktion aus und gibt keine Daten zurück. Sie dient lediglich zur Speicherung der Abfrageinformationen. Nachdem Sie eine Abfrage erstellt haben, müssen Sie sie ausführen, damit Daten abgerufen werden.  
  
 LINQ to Entities-Abfragen können in zwei verschiedenen Syntaxarten verfasst werden: in der Abfrageausdrucksyntax und in der methodenbasierten Abfragesyntax. Die Abfrageausdruckssyntax und die methodenbasierte Abfragesyntax sind neu in C# 3.0 und Visual Basic 9.0.  
  
 Weitere Informationen finden Sie unter [Abfragen in LINQ to Entities](queries-in-linq-to-entities.md).  
  
## <a name="query-conversion"></a>Konvertieren von Abfragen  
 Um eine LINQ to Entities-Abfrage für das Entity Framework auszuführen, muss die LINQ-Abfrage in eine Befehlsstrukturdarstellung umgewandelt werden, die für das Entity Framework ausgeführt werden kann.  
  
 LINQ to Entities Abfragen bestehen aus LINQ-Standard Abfrage Operatoren (z <xref:System.Linq.Queryable.Select%2A> . b., <xref:System.Linq.Queryable.Where%2A> und <xref:System.Linq.Queryable.GroupBy%2A> ) und Ausdrücken (x > 10, Contact. LastName usw.). LINQ-Operatoren werden nicht von einer Klasse definiert, sondern sind Methoden für eine Klasse. In LINQ können Ausdrücke alles enthalten, was für Typen im <xref:System.Linq.Expressions>-Namespace zulässig ist, und durch Erweiterung alles, was als Lambda-Funktion dargestellt werden kann. Damit sind sie den Ausdrücken übergeordnet, die im Entity Framework verwendet werden können. Diese sind per Definition auf Operationen beschränkt, die auf der Datenbank zulässig sind und von <xref:System.Data.Objects.ObjectQuery%601> unterstützt werden.  
  
 Im Entity Framework werden sowohl Operatoren als auch Ausdrücke in einer einzigen Typhierarchie dargestellt, die anschließend in die Befehlsstruktur eingefügt wird. Mithilfe der Befehlsstruktur führt das Entity Framework die Abfrage aus. Wenn die LINQ-Abfrage nicht als Befehlsstruktur ausgedrückt werden kann, wird beim Konvertieren der Abfrage eine Ausnahme ausgelöst. Zur Konvertierung von LINQ to Entities-Abfragen gehören die folgenden zwei untergeordneten Konvertierungen: die Umwandlung der Standardabfrageoperatoren und die Konvertierung der Ausdrücke.  
  
 Für eine Reihe von LINQ-Standardabfrageoperatoren gibt es keine gültige Übersetzung in LINQ to Entities. Die Verwendung dieser Operatoren löst bei der Übersetzung der Abfrage eine Ausnahme aus. Eine Liste der unterstützten LINQ to Entities-Operatoren finden Sie [unter Unterstützte und nicht unterstützte LINQ-Methoden (LINQ to Entities)](supported-and-unsupported-linq-methods-linq-to-entities.md).  
  
 Weitere Informationen zur Verwendung der Standard Abfrage Operatoren in LINQ to Entities finden Sie unter [Standard Abfrage Operatoren in LINQ to Entities Abfragen](standard-query-operators-in-linq-to-entities-queries.md).  
  
 Im Allgemeinen werden Ausdrücke in LINQ to Entities auf dem Server ausgewertet, daher dürfte sich das Verhalten der Ausdrücke nicht nach der CLR-Semantik richten. Weitere Informationen finden Sie unter [Ausdrücke in LINQ to Entities Abfragen](expressions-in-linq-to-entities-queries.md).  
  
 Informationen dazu, wie CLR-Methodenaufrufe kanonischen Funktionen in der Datenquelle zugeordnet werden, finden Sie unterzuordnen von [CLR-Methoden zu kanonischen](clr-method-to-canonical-function-mapping.md)Funktionen.  
  
 Weitere Informationen zum Aufrufen von kanonischen, Datenbank-und benutzerdefinierten Funktionen in LINQ to Entities Abfragen finden Sie unter [Aufrufen von Funktionen in LINQ to Entities Abfragen](calling-functions-in-linq-to-entities-queries.md).  
  
## <a name="query-execution"></a>Abfrageausführung  
 Nachdem der Benutzer die LINQ-Abfrage erstellt hat, wird sie in eine Darstellung konvertiert, die mit dem Entity Framework kompatibel ist (in Form von Befehlsstrukturen). Diese wird anschließend für die Datenquelle ausgeführt. Bei der Abfrageausführung werden alle Abfrageausdrücke (oder Abfragekomponenten) auf dem Client oder dem Server ausgewertet. Dazu gehören Ausdrücke, die zur Materialisierung der Ergebnisse oder zur Entitätsprojektion verwendet werden. Weitere Informationen finden Sie unter [Abfrage Ausführung](query-execution.md). Informationen dazu, wie die Leistung verbessert wird, indem eine Abfrage einmal kompiliert und dann mehrmals mit verschiedenen Parametern ausgeführt wird, finden Sie unter [kompilierte Abfragen (LINQ to Entities)](compiled-queries-linq-to-entities.md).  
  
## <a name="materialization"></a>Materialisierung  
 Als Materialisierung wird das Zurückgeben von Abfrageergebnissen in Form von CLR-Typen an den Client bezeichnet. In LINQ to Entities werden Datensätze mit Abfrageergebnissen nie zurückgegeben. Es ist immer ein Sicherungs-CLR-Typ vorhanden, der vom Benutzer oder vom Entity Framework definiert oder vom Compiler generiert wird (anonyme Typen). Jede Objektmaterialisierung wird vom Entity Framework durchgeführt. Alle Fehler, die dadurch entstehen, dass zwischen dem Entity Framework und der CLR keine Zuordnung vorgenommen werden kann, lösen bei der Objektmaterialisierung Ausnahmen aus.  
  
 Abfrageergebnisse werden üblicherweise auf eine der folgenden Arten zurückgegeben:  
  
- Eine Auflistung von 0 (null) oder mehr typisierten Entitätsobjekten oder eine Projektion komplexer Typen, die im konzeptionellen Modell definiert werden.  
  
- CLR-Typen, die vom Entity Framework unterstützt werden.  
  
- Inlineauflistungen  
  
- Anonyme Typen  
  
 Weitere Informationen finden Sie unter [Abfrageergebnisse](query-results.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Abfragen in LINQ to Entities](queries-in-linq-to-entities.md)  
  
 [Ausdrücke in LINQ to Entities-Abfragen](expressions-in-linq-to-entities-queries.md)  
  
 [Aufrufen von Funktionen in LINQ to Entities-Abfragen](calling-functions-in-linq-to-entities-queries.md)  
  
 [Kompilierte Abfragen (LINQ to Entities)](compiled-queries-linq-to-entities.md)  
  
 [Abfrageausführung](query-execution.md)  
  
 [Abfrageergebnisse](query-results.md)  
  
 [Standardabfrageoperatoren in LINQ to Entities-Abfragen](standard-query-operators-in-linq-to-entities-queries.md)  
  
 [Zuordnen von CLR-Methoden zu kanonischen Funktionen](clr-method-to-canonical-function-mapping.md)  
  
 [Unterstützte und nicht unterstützte LINQ-Methoden (LINQ to Entities)](supported-and-unsupported-linq-methods-linq-to-entities.md)  
  
 [Bekannte Probleme von und Überlegungen zu LINQ to Entities](known-issues-and-considerations-in-linq-to-entities.md)  
  
## <a name="see-also"></a>Siehe auch

- [Bekannte Probleme von und Überlegungen zu LINQ to Entities](known-issues-and-considerations-in-linq-to-entities.md)
- [Language Integrated Query (LINQ) – C#](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [Language Integrated Query (LINQ) – Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ und ADO.NET](../../linq-and-ado-net.md)
- [ADO.NET Entity Framework](../index.md)
