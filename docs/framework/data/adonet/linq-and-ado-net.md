---
title: LINQ und ADO.NET
ms.date: 03/30/2017
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
ms.openlocfilehash: 312eb4b1c0512ca1244daec5bcda3ed864c3646d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878330"
---
# <a name="linq-and-adonet"></a>LINQ und ADO.NET
Heute verwenden viele Entwickler von Geschäftsanwendungen müssen zwei (oder mehr) Programmiersprache arbeiten: einer allgemeinen Programmiersprache für die Geschäftsschichten Geschäftslogik und präsentationsebenen (z. B. Visual c# oder Visual Basic), und eine Abfragesprache für die Interaktion mit der Datenbank (z. B. [!INCLUDE[tsql](../../../../includes/tsql-md.md)]). Der Entwickler muss also mehrerer Sprachen mächtig sein, um seine Arbeit effektiv erledigen zu können. Außerdem sind dadurch Sprachkonflikte in der Entwicklungsumgebung vorprogrammiert. So ergibt es sich z. B., dass eine Anwendung, die zur Ausführung einer Abfrage von Daten aus einer Datenbank eine Datenzugriffs-API verwendet, die Abfrage als Zeichenfolgenliteral angibt, indem sie Anführungszeichen verwendet. Diese Abfrage ist jedoch für den Compiler nicht lesbar und wird nicht auf Fehler (Syntaxfehler, tatsächliche Existenz der Spalten oder Zeilen, auf die verwiesen wird, usw.) geprüft. Auch der Typ der Abfrageparameter wird nicht geprüft, und es gibt keine `IntelliSense`-Unterstützung.  
  
 In [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] können Entwickler in ihrem Anwendungscode mengenbasierte Abfragen unterbringen, ohne dazu auf eine separate Abfragesprache zurückgreifen zu müssen. Sie können [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Abfragen für die verschiedensten aufzählbaren Datenquellen (also Datenquellen, die die <xref:System.Collections.IEnumerable>-Schnittstelle implementieren) schreiben, wie Datenstrukturen, XML-Dokumente, SQL-Datenbanken und <xref:System.Data.DataSet>-Objekte im Arbeitsspeicher. Auch wenn diese aufzählbaren Datenquellen auf unterschiedliche Art und Weise implementiert sind, weisen sie doch alle dieselben Syntax- und Sprachkonstrukte auf. Da Abfragen direkt in der Programmiersprache formuliert werden können, benötigen Sie keine andere Abfragesprache, mit der Abfragen als Zeichenfolgenliterale eingebettet werden, die vom Compiler weder gelesen noch geprüft werden können. Ermöglicht die Integration von Abfragen in die Programmiersprache auch Visual Studio-Programmierern, produktiver zu sein, indem Sie Kompilierzeittyp und syntaxprüfungen und `IntelliSense`. Mit diesen Funktionen wird der für die Beseitigung von Abfragefehlern erforderliche Aufwand beträchtlich reduziert.  
  
 Das Übertragen von Daten aus SQL-Tabellen in Objekte im Arbeitsspeicher ist häufig nervenaufreibend und fehleranfällig. Der von [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] und [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] implementierte [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]-Anbieter konvertiert die Quelldaten in <xref:System.Collections.IEnumerable>-basierte Objektauflistungen. Dem Programmierer werden die Daten stets als <xref:System.Collections.IEnumerable>-Auflistung angezeigt, gleich ob bei einer Abfrage oder bei einem Update. Für das Schreiben von Abfragen für diese Auflistungen steht uneingeschränkte `IntelliSense`-Unterstützung zur Verfügung.  
  
 Es gibt drei separate ADO.NET-[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]-Technologien: [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] und [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] ermöglicht umfangreichere, optimierte Abfragen der <xref:System.Data.DataSet> und [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] ermöglicht es Ihnen, SQL Server-Datenbankschemas direkt abzufragen und [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] können Sie Abfragen ein [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].  
  
 Das folgende Diagramm ermöglicht eine Einordnung der ADO.NET LINQ-Technologien im Kontext von allgemeinen Programmiersprachen und anderen LINQ-fähigen Datenquellen.  
  
 ![LINQ to ADO.NET overview](../../../../docs/framework/data/adonet/media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 Weitere Informationen über LINQ finden Sie unter [Language Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md).
  
 Die folgenden Abschnitte enthalten weitere Informationen zu [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] und [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 Die <xref:System.Data.DataSet> ist ein Schlüsselelement des getrennten Programmiermodells, die ADO.NET basiert auf und ist branchenweit verbreitet. Mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] können Entwickler umfangreichere Abfragefunktionen in <xref:System.Data.DataSet> integrieren, indem Sie denselben Abfrageformulierungsmechanismus verwenden, der auch für viele andere Datenquellen zur Verfügung steht. Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] ist ein nützliches Tool für Entwickler, die keine Zuordnung zu einem Konzeptmodell benötigen. Mit [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] können Sie das [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Programmiermodell direkt über das vorhandene Datenbankschema verwenden. [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] ermöglicht Entwicklern von .NET Framework-Klassen zu generieren, die Daten darstellen. Diese generierten Klassen werden nicht einem Konzeptdatenmodell zugeordnet, sondern die Zuordnung erfolgt direkt zu Datenbanktabellen, Ansichten, gespeicherten Prozeduren und benutzerdefinierten Funktionen.  
  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] ermöglicht es Entwicklern, Code direkt für das Speicherschema zu schreiben und dabei zusätzlich zu anderen Datenquellen, z. B. XML, dasselbe [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Programmierungsmuster wie bei Auflistungen im Arbeitsspeicher und beim <xref:System.Data.DataSet> zu verwenden. Weitere Informationen finden Sie unter [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Die meisten aktuellen Anwendungen basieren auf relationalen Datenbanken. Daher müssen diese Anwendungen mit den relational abgebildeten Daten interagieren. Datenbankschemas sind nicht immer optimal für das Erstellen von Anwendungen geeignet, und die konzeptionellen Modelle von Anwendungen weichen von den logischen Modellen der Datenbanken ab. Das [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] stellt ein konzeptionelles Datenmodell dar, das für den Entwurf der Daten einer bestimmten Domäne verwendet werden kann, sodass Anwendungen mit den Daten als Entitäten bzw. Objekte interagieren können. Finden Sie unter [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) für Weitere Informationen.  
  
 Durch das [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] werden relationale Daten als Objekte in der .NET-Umgebung verfügbar gemacht. Dadurch wird die Objektebene zu einem optimalen Ziel für die [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Unterstützung, die es Entwicklern ermöglicht, Abfragen an die Datenbank in der Sprache der Geschäftlogik zu formulieren. Dies wird als [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] bezeichnet. Weitere Informationen Sie unter [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)
- [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)
- [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
- [Language-Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
