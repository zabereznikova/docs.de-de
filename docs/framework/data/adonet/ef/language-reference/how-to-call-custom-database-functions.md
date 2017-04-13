---
title: "Gewusst wie: Aufrufen von benutzerdefinierten Datenbankfunktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gewusst wie: Aufrufen von benutzerdefinierten Datenbankfunktionen
In diesem Thema wird das Aufrufen von benutzerdefinierten Funktionen beschrieben, die in der Datenbank in LINQ to Entities\-Abfragen definiert werden.  
  
 Datenbankfunktionen, die von LINQ to Entities\-Abfragen aufgerufen werden, werden in der Datenbank ausgeführt.  Das Ausführen von Funktionen in der Datenbank kann die Anwendungsleistung verbessern.  
  
 Die folgende Prozedur stellt in knapper Form dar, wie eine benutzerdefinierte Datenbankfunktion aufgerufen wird.  Das folgende Beispiel enthält weitere Details zu den Schritten in der Prozedur.  
  
### So rufen Sie benutzerdefinierte Funktionen auf, die in der Datenbank definiert sind  
  
1.  Erstellen Sie in der Datenbank eine benutzerdefinierte Funktion.  
  
     Weitere Informationen zum Erstellen von benutzerdefinierten Funktionen in SQL Server finden Sie unter [CREATE FUNCTION \(Transact\-SQL\)](http://go.microsoft.com/fwlink/?LinkID=139871).  
  
2.  Beschreiben Sie in der Datenspeicherschema\-Definitionssprache \(SSDL\) der EDMX\-Datei eine Funktion.  Der Name der Funktion muss mit der in der Datenbank deklarierten Funktion übereinstimmen.  
  
     Weitere Informationen finden Sie unter [Function Element \(SSDL\)](http://msdn.microsoft.com/de-de/b60cfc3d-8b93-423e-8c99-b867256640a4).  
  
3.  Fügen Sie einer Klasse im Anwendungscode eine entsprechende Methode hinzu, und übernehmen Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> für die Methode. Der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A>\-Parameter und der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A>\-Parameter des Attributs sind die Namespacebezeichnung des konzeptionellen Modells bzw. der Funktionsname im konzeptionellen Modell.  Bei der Funktionsnamenauflösung für LINQ wird die Groß\-\/Kleinschreibung berücksichtigt.  
  
4.  Rufen Sie die Methode in einer LINQ to Entities\-Abfrage auf.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine benutzerdefinierte Datenbankfunktion innerhalb einer LINQ to Entities\-Abfrage aufgerufen wird.  Im Beispiel wird das Modell "School" verwendet.  Weitere Informationen zum Modell "School" finden Sie unter [Creating the School Sample Database](http://msdn.microsoft.com/de-de/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) und [Generating the School .edmx File](http://msdn.microsoft.com/de-de/c48b3907-a8be-4fe6-884c-e95af1852758).  
  
 Der folgende Code fügt die `AvgStudentGrade`\-Funktion der Beispieldatenbank "School" hinzu.  
  
> [!NOTE]
>  Die Schritte zum Aufrufen einer benutzerdefinierten Datenbankfunktion sind unabhängig vom Datenbankserver identisch.  Der folgende Code wird jedoch speziell für die Erstellung einer Funktion in einer SQL Server\-Datenbank verwendet.  Der Code zum Erstellen einer benutzerdefinierten Funktion in einem anderen Datenbankserver kann ggf. abweichen.  
  
 [!code-sql[DP L2E MapToDBFunction#1](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]  
  
## Beispiel  
 Beschreiben Sie nun in der Datenspeicherschema\-Definitionssprache \(SSDL\) der EDMX\-Datei eine Funktion.  Der folgenden Code beschreibt die `AvgStudentGrade`\-Funktion in SSDL:  
  
 [!code-xml[DP L2E MapToDBFunction#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]  
  
## Beispiel  
 Erstellen Sie jetzt eine Methode, und ordnen Sie sie der in der SSDL beschriebenen Funktion zu.  Die Methode in der folgenden Klasse wird der Funktion zugeordnet, die in der SSDL \(oben\) mithilfe eines <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> definiert wurde.  Wird diese Methode aufgerufen, wird die entsprechende Funktion in der Datenbank ausgeführt.  
  
 [!code-csharp[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
 [!code-vb[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]  
  
## Beispiel  
 Rufen Sie schließlich die Methode in einer LINQ to Entities\-Abfrage auf.  Im folgenden Code werden die Nachnamen und Durchschnittsnoten von Schülern auf der Konsole angezeigt:  
  
 [!code-csharp[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
 [!code-vb[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]  
  
## Siehe auch  
 [.edmx File Overview](http://msdn.microsoft.com/de-de/f4c8e7ce-1db6-417e-9759-15f8b55155d4)   
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)