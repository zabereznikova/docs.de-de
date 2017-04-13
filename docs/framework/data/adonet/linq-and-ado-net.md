---
title: "LINQ und ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
caps.latest.revision: 8
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 8
---
# LINQ und ADO.NET
Unter den heutigen Bedingungen müssen viele Entwickler von Geschäftsanwendungen mit zwei \(oder mehr\) Programmiersprachen arbeiten: mit einer allgemeinen Programmiersprache für die Geschäftslogik\- und die Darstellungsschicht \(wie [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] oder [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\) und einer Abfragesprache für die Interaktion mit der Datenbank \(z. B. [!INCLUDE[tsql](../../../../includes/tsql-md.md)]\).  Der Entwickler muss also mehrerer Sprachen mächtig sein, um seine Arbeit effektiv erledigen zu können. Außerdem sind dadurch Sprachkonflikte in der Entwicklungsumgebung vorprogrammiert.  So ergibt es sich z. B., dass eine Anwendung, die zur Ausführung einer Abfrage von Daten aus einer Datenbank eine Datenzugriffs\-API verwendet, die Abfrage als Zeichenfolgenliteral angibt, indem sie Anführungszeichen verwendet.  Diese Abfrage ist jedoch für den Compiler nicht lesbar und wird nicht auf Fehler \(Syntaxfehler, tatsächliche Existenz der Spalten oder Zeilen, auf die verwiesen wird, usw.\) geprüft.  Auch der Typ der Abfrageparameter wird nicht geprüft, und es gibt keine `IntelliSense`\-Unterstützung.  
  
 In [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] können Entwickler in ihrem Anwendungscode mengenbasierte Abfragen unterbringen, ohne dazu auf eine separate Abfragesprache zurückgreifen zu müssen.  Sie können [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]\-Abfragen für die verschiedensten aufzählbaren Datenquellen \(also Datenquellen, die die <xref:System.Collections.IEnumerable>\-Schnittstelle implementieren\) schreiben, wie Datenstrukturen, XML\-Dokumente, SQL\-Datenbanken und <xref:System.Data.DataSet>\-Objekte im Arbeitsspeicher.  Auch wenn diese aufzählbaren Datenquellen auf unterschiedliche Art und Weise implementiert sind, weisen sie doch alle dieselben Syntax\- und Sprachkonstrukte auf.  Da Abfragen direkt in der Programmiersprache formuliert werden können, benötigen Sie keine andere Abfragesprache, mit der Abfragen als Zeichenfolgenliterale eingebettet werden, die vom Compiler weder gelesen noch geprüft werden können.  Durch die Integration von Abfragen in die Programmiersprache werden [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]\-Programmierer auch in die Lage versetzt, durch Typ\- und Syntaxprüfungen während der Kompilierung sowie `IntelliSense`\-Unterstützung produktiver zu arbeiten.  Mit diesen Funktionen wird der für die Beseitigung von Abfragefehlern erforderliche Aufwand beträchtlich reduziert.  
  
 Das Übertragen von Daten aus SQL\-Tabellen in Objekte im Arbeitsspeicher ist häufig nervenaufreibend und fehleranfällig.  Der von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] und [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] implementierte [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]\-Anbieter konvertiert die Quelldaten in <xref:System.Collections.IEnumerable>\-basierte Objektauflistungen.  Dem Programmierer werden die Daten stets als <xref:System.Collections.IEnumerable>\-Auflistung angezeigt, gleich ob bei einer Abfrage oder bei einem Update.  Für das Schreiben von Abfragen für diese Auflistungen steht uneingeschränkte `IntelliSense`\-Unterstützung zur Verfügung.  
  
 Es gibt drei separate ADO.NET\-[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]\-Technologien: [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] und [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)].  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] ermöglicht umfangreichere, optimierte Abfragen der <xref:System.Data.DataSet>\-Daten, mit [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] können Sie [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]\-Datenbankschemas direkt abfragen, und mit [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] können Sie ein [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] abfragen.  
  
 Das folgende Diagramm ermöglicht eine Einordnung der ADO.NET LINQ\-Technologien im Kontext von allgemeinen Programmiersprachen und anderen LINQ\-fähigen Datenquellen.  
  
 ![Übersicht über LINQ to ADO.NET](../../../../docs/framework/data/adonet/media/dpue-linqtoadonetoverview-bpuedev11.png "DPUE\_LinqToAdoNetOverview\_bpuedev11")  
  
 Allgemeinere Informationen zu den LINQ\-Sprachfunktionen finden Sie unter [Introduction to LINQ](../../../../ocs/visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  Informationen über die Verwendung von LINQ in Ihren Anwendungen finden Sie im [NOT IN BUILD: LINQ General Programming Guide](http://msdn.microsoft.com/de-de/609c7a6b-cbdd-429d-99f3-78d13d3bc049). In diesem Handbuch finden Sie detaillierte Informationen über die Verwendung von LINQ\-Technologien.  
  
 Die folgenden Abschnitte enthalten weitere Informationen zu [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] und [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)].  
  
## LINQ to DataSet  
 Das <xref:System.Data.DataSet>\-Objekt ist ein wichtiges und weit verbreitetes Element des getrennten Programmiermodells, auf dem [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] basiert.  Mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] können Entwickler umfangreichere Abfragefunktionen in <xref:System.Data.DataSet> integrieren, indem Sie denselben Abfrageformulierungsmechanismus verwenden, der auch für viele andere Datenquellen zur Verfügung steht.  Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] ist ein nützliches Tool für Entwickler, die keine Zuordnung zu einem Konzeptmodell benötigen.  Mit [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] können Sie das [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]\-Programmiermodell direkt über das vorhandene Datenbankschema verwenden.  [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] ermöglicht es Entwicklern, [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Klassen zu generieren, die Daten darstellen.  Diese generierten Klassen werden nicht einem Konzeptdatenmodell zugeordnet, sondern die Zuordnung erfolgt direkt zu Datenbanktabellen, Ansichten, gespeicherten Prozeduren und benutzerdefinierten Funktionen.  
  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] ermöglicht es Entwicklern, Code direkt für das Speicherschema zu schreiben und dabei zusätzlich zu anderen Datenquellen, z. B. XML, dasselbe [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]\-Programmierungsmuster wie bei Auflistungen im Arbeitsspeicher und beim <xref:System.Data.DataSet> zu verwenden.  Weitere Informationen finden Sie unter [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
## LINQ to Entities  
 Die meisten aktuellen Anwendungen basieren auf relationalen Datenbanken.  Daher müssen diese Anwendungen mit den relational abgebildeten Daten interagieren.  Datenbankschemas sind nicht immer optimal für das Erstellen von Anwendungen geeignet, und die konzeptionellen Modelle von Anwendungen weichen von den logischen Modellen der Datenbanken ab.  Das [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] stellt ein konzeptionelles Datenmodell dar, das für den Entwurf der Daten einer bestimmten Domäne verwendet werden kann, sodass Anwendungen mit den Daten als Entitäten bzw. Objekte interagieren können.  Weitere Informationen finden Sie unter [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).  
  
 Durch das [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] werden relationale Daten als Objekte in der .NET\-Umgebung verfügbar gemacht.  Dadurch wird die Objektebene zu einem optimalen Ziel für die [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]\-Unterstützung, die es Entwicklern ermöglicht, Abfragen an die Datenbank in der Sprache der Geschäftlogik zu formulieren.  Dies wird als [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] bezeichnet.  Weitere Informationen finden Sie unter [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## Siehe auch  
 [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)   
 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)   
 [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)