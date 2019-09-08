---
title: LINQ und ADO.NET
ms.date: 03/30/2017
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
ms.openlocfilehash: d354e2e7f2696e90845edf0348340986fd7bb83c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795185"
---
# <a name="linq-and-adonet"></a>LINQ und ADO.NET
Heutzutage müssen viele Entwickler von Unternehmen zwei (oder mehr) Programmiersprachen verwenden: eine Sprache auf hoher Ebene für die Geschäftslogik und Präsentations Schichten (z. C# b. Visual oder Visual Basic) und eine Abfragesprache für die Interaktion mit der Datenbank (z. b. Transact-SQL). . Der Entwickler muss also mehrerer Sprachen mächtig sein, um seine Arbeit effektiv erledigen zu können. Außerdem sind dadurch Sprachkonflikte in der Entwicklungsumgebung vorprogrammiert. So ergibt es sich z. B., dass eine Anwendung, die zur Ausführung einer Abfrage von Daten aus einer Datenbank eine Datenzugriffs-API verwendet, die Abfrage als Zeichenfolgenliteral angibt, indem sie Anführungszeichen verwendet. Diese Abfrage ist jedoch für den Compiler nicht lesbar und wird nicht auf Fehler (Syntaxfehler, tatsächliche Existenz der Spalten oder Zeilen, auf die verwiesen wird, usw.) geprüft. Auch der Typ der Abfrageparameter wird nicht geprüft, und es gibt keine `IntelliSense`-Unterstützung.  
  
 In [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] können Entwickler in ihrem Anwendungscode mengenbasierte Abfragen unterbringen, ohne dazu auf eine separate Abfragesprache zurückgreifen zu müssen. Sie können [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Abfragen für die verschiedensten aufzählbaren Datenquellen (also Datenquellen, die die <xref:System.Collections.IEnumerable>-Schnittstelle implementieren) schreiben, wie Datenstrukturen, XML-Dokumente, SQL-Datenbanken und <xref:System.Data.DataSet>-Objekte im Arbeitsspeicher. Auch wenn diese aufzählbaren Datenquellen auf unterschiedliche Art und Weise implementiert sind, weisen sie doch alle dieselben Syntax- und Sprachkonstrukte auf. Da Abfragen direkt in der Programmiersprache formuliert werden können, benötigen Sie keine andere Abfragesprache, mit der Abfragen als Zeichenfolgenliterale eingebettet werden, die vom Compiler weder gelesen noch geprüft werden können. Durch die Integration von Abfragen in die Programmiersprache können Visual Studio-Programmierer auch produktiver arbeiten, indem Sie die Typ-und Syntax Überprüfung `IntelliSense`für die Kompilierzeit bereitstellen, und. Mit diesen Funktionen wird der für die Beseitigung von Abfragefehlern erforderliche Aufwand beträchtlich reduziert.  
  
 Das Übertragen von Daten aus SQL-Tabellen in Objekte im Arbeitsspeicher ist häufig nervenaufreibend und fehleranfällig. Der [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] von implementierte Anbieter LINQ to DataSet [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] und konvertiert die Quelldaten <xref:System.Collections.IEnumerable>in-basierte Objekt Auflistungen. Dem Programmierer werden die Daten stets als <xref:System.Collections.IEnumerable>-Auflistung angezeigt, gleich ob bei einer Abfrage oder bei einem Update. Für das Schreiben von Abfragen für diese Auflistungen steht uneingeschränkte `IntelliSense`-Unterstützung zur Verfügung.  
  
 Es gibt drei separate [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]-Technologien für ADO.NET: LINQ to DataSet, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] und LINQ to Entities. LINQ to DataSet bietet umfangreichere, optimierte Abfragen für die <xref:System.Data.DataSet> und [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] ermöglicht es Ihnen, SQL Server Datenbankschemas direkt abzufragen, und LINQ to Entities ermöglicht es Ihnen, eine Entity Data Model abzufragen.  
  
 Das folgende Diagramm ermöglicht eine Einordnung der ADO.NET LINQ-Technologien im Kontext von allgemeinen Programmiersprachen und anderen LINQ-fähigen Datenquellen.  
  
 ![Übersicht über LINQ to ADO.net](./media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 Weitere Informationen zu LINQ finden Sie unter [Language Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md).
  
 In den folgenden Abschnitten finden Sie weitere Informationen zu [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]LINQ to DataSet, und LINQ to Entities.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> Ist ein Schlüsselelement des getrennten Programmiermodells, auf dem ADO.NET basiert, und wird häufig verwendet. LINQ to DataSet ermöglicht es Entwicklern, umfangreichere Abfragefunktionen <xref:System.Data.DataSet> in zu erstellen, indem Sie denselben Abfrage Formulierungs Mechanismus verwenden, der auch für viele andere Datenquellen verfügbar ist. Weitere Informationen finden Sie unter [LINQ to DataSet](linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] ist ein nützliches Tool für Entwickler, die keine Zuordnung zu einem Konzeptmodell benötigen. Mit [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] können Sie das [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Programmiermodell direkt über das vorhandene Datenbankschema verwenden. [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]ermöglicht es Entwicklern, .NET Framework Klassen zu generieren, die Daten darstellen. Diese generierten Klassen werden nicht einem Konzeptdatenmodell zugeordnet, sondern die Zuordnung erfolgt direkt zu Datenbanktabellen, Ansichten, gespeicherten Prozeduren und benutzerdefinierten Funktionen.  
  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] ermöglicht es Entwicklern, Code direkt für das Speicherschema zu schreiben und dabei zusätzlich zu anderen Datenquellen, z. B. XML, dasselbe [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Programmierungsmuster wie bei Auflistungen im Arbeitsspeicher und beim <xref:System.Data.DataSet> zu verwenden. Weitere Informationen finden Sie unter [LINQ to SQL](./sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Die meisten aktuellen Anwendungen basieren auf relationalen Datenbanken. Daher müssen diese Anwendungen mit den relational abgebildeten Daten interagieren. Datenbankschemas sind nicht immer optimal für das Erstellen von Anwendungen geeignet, und die konzeptionellen Modelle von Anwendungen weichen von den logischen Modellen der Datenbanken ab. Der Entity Data Model ist ein konzeptionelles Datenmodell, das verwendet werden kann, um die Daten einer bestimmten Domäne zu modellieren, sodass Anwendungen mit Daten als Objekte interagieren können. Weitere Informationen finden Sie unter [ADO.NET Entity Framework](./ef/index.md) .  
  
 Durch das Entity Data Model werden relationale Daten als Objekte in der .NET-Umgebung verfügbar gemacht. Dadurch wird die Objektebene zu einem optimalen Ziel für die [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Unterstützung, die es Entwicklern ermöglicht, Abfragen an die Datenbank in der Sprache der Geschäftlogik zu formulieren. Dies wird auch als LINQ to Entities bezeichnet. Weitere Informationen Sie unter [LINQ to Entities](./ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to DataSet](linq-to-dataset.md)
- [LINQ to SQL](./sql/linq/index.md)
- [LINQ to Entities](./ef/language-reference/linq-to-entities.md)
- [Language-Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
