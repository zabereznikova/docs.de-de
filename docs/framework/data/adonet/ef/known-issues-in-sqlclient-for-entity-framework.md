---
title: "Bekannte Probleme mit SqlClient f&#252;r Entity Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 48fe4912-4d0f-46b6-be96-3a42c54780f6
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Bekannte Probleme mit SqlClient f&#252;r Entity Framework
In diesem Abschnitt werden bekannte Probleme im Zusammenhang mit dem .NET Framework\-Datenanbieter für SQL Server \(SqlClient\) beschrieben.  
  
## Nachfolgende Leerzeichen in Zeichenfolgenfunktionen  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] ignoriert nachfolgende Leerzeichen in Zeichenfolgenwerten.  Deshalb kann die Übergabe von nachfolgenden Leerzeichen in der Zeichenfolge zu unvorhersehbaren Ergebnissen und sogar zu Fehlern führen.  
  
 Wenn nachfolgende Leerzeichen in der Zeichenfolge unumgänglich sind, sollten Sie am Ende ein Leerstellenzeichen hinzufügen, sodass [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] die Zeichenfolge nicht abtrennt.  Wenn die nachfolgenden Leerzeichen nicht benötigt werden, sollten sie vor der Übergabe an die Abfragepipeline abgetrennt werden.  
  
## RIGHT\-Funktion  
 Wenn ein Wert, der nicht `null` ist, als erstes Argument und 0 als zweites Argument an `RIGHT(nvarchar(max)`, 0`)` oder `RIGHT(varchar(max)`, 0`)` übergeben wird, wird der Wert `NULL` anstelle einer Zeichenfolge, die `empty` ist, zurückgegeben.  
  
## CROSS\- und OUTER APPLY\-Operatoren  
 CROSS\- und OUTER APPLY\-Operatoren wurden in [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)] eingeführt.  In einigen Fällen liefert die Abfragepipeline möglicherweise eine Transact\-SQL\-Anweisung, die CROSS APPLY\- und\/oder OUTER APPLY\-Operatoren enthält.  Da einige Back\-End\-Anbieter, einschließlich [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]\-Versionen, die älter sind als [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], diese Operatoren nicht unterstützen, können solche Abfragen auf diesen Back\-End\-Anbietern nicht ausgeführt werden.  
  
 Dies sind einige typische Szenarios, die möglicherweise zum Auftreten von CROSS APPLY\- und\/oder OUTER APPLY\-Operatoren in der Ausgabeabfrage führen:  
  
-   Eine korrelierte Unterabfrage mit Paging.  
  
-   Ein `AnyElement` über einer korrelierten Unterabfrage oder über einer von der Navigation erzeugten Auflistung.  
  
-   LINQ\-Abfragen, in denen Gruppierungsmethoden verwendet werden, die einen Elementselektor akzeptieren.  
  
-   Eine Abfrage, in der ein CROSS APPLY oder ein OUTER APPLY explizit angegeben wird  
  
-   Eine Abfrage, die über ein DEREF\-Konstrukt über einem REF\-Konstrukt verfügt.  
  
## SKIP\-Operator  
 Wenn Sie [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] verwenden, führt die Verwendung von SKIP mit ORDER BY auf Nichtschlüsselspalten möglicherweise zur Rückgabe falscher Ergebnisse.  Es kann vorkommen, dass mehr als die angegebene Anzahl von Zeilen übersprungen wird, wenn die Nichtschlüsselspalte Daten doppelt enthält.  Der Grund dafür ist die Übersetzung von **SKIP** für [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].  In der folgenden Abfrage können beispielsweise mehr als fünf Zeilen übersprungen werden, wenn `E.NonKeyColumn` Werte doppelt enthält:  
  
```  
SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L  
```  
  
## Verwenden der richtigen SQL Server\-Version  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verarbeitet die [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]\-Abfrage auf Grundlage der SQL Server\-Version, die im `ProviderManifestToken`\-Attribut des Schemaelements in der Speichermodelldatei \(SSDL\) angegeben ist.  Diese Version unterscheidet sich möglicherweise von der tatsächlichen SQL Server\-Version, mit der Sie verbunden sind.  Wenn Sie beispielsweise SQL Server 2005 verwenden, aber das `ProviderManifestToken`\-Attribut auf 2008 festgelegt ist, wird die generierte [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]\-Abfrage u. U. nicht auf dem Server ausgeführt. Zum Beispiel wird eine Abfrage für die neuen Date\- und Time\-Typen, die in SQL Server 2008 eingeführt wurden, unter früheren Versionen von SQL Server nicht ausgeführt.  Wenn Sie SQL Server 2005 verwenden, das `ProviderManifestToken`\-Attribut jedoch auf 2000 festgelegt ist, ist die generierte [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]\-Abfrage möglicherweise weniger optimiert, oder es wird eine Ausnahme ausgelöst, die besagt, dass die Abfrage nicht unterstützt wird.  Weitere Informationen finden Sie oben im Abschnitt über die CROSS\- und OUTER APPLY\-Operatoren.  
  
 Bestimmte Datenbankverhaltensweisen hängen vom festgelegten Kompatibilitätsgrad der Datenbank ab.  Wenn das `ProviderManifestToken`\-Attribut auf 2005 festgelegt ist und Sie über die SQL Server\-Version 2005 verfügen, der Kompatibilitätsgrad einer Datenbank jedoch auf "80" \(SQL Server 2000\) festgelegt ist, zielt das erzeugte [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] zwar auf SQL Server 2005 ab, wird aber aufgrund der Einstellung für den Kompatibilitätsgrad möglicherweise nicht wie erwartet ausgeführt.  Zum Beispiel geht möglicherweise die Sortierung verloren, wenn ein Spaltenname in der ORDER BY\-Liste einem Spaltennamen im Selektor entspricht.  
  
## Geschachtelte Abfragen in Projektion  
 Geschachtelte Abfragen in einer Projektionsklausel könnten auf dem Server in Abfragen des kartesischen Produkts übersetzt werden.  Auf einigen Back\-End\-Servern, einschließlich SQL Server, kann dies zu einer sehr großen TempDB\-Tabelle führen.  Dies kann die Serverleistung beeinträchtigen.  
  
 Im Folgenden sehen Sie ein Beispiel für eine geschachtelte Abfrage in einer Projektionsklausel:  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## Servergenerierte GUID\-Identitätswerte  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] unterstützt servergenerierte GUID\-Typidentitätswerte, aber der Anbieter muss die Rückgabe von servergenerierten Identitätswerten nach dem Einfügen einer Zeile unterstützen.  Beginnend mit [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2005 können Sie den servergenerierten GUID\-Typ in einer [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]\-Datenbank durch die [OUTPUT\-Klausel](http://go.microsoft.com/fwlink/?LinkId=169400) zurückgeben.  
  
## Siehe auch  
 [SqlClient für das Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)   
 [Bekannte Probleme von und Überlegungen zu LINQ to Entities](../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)