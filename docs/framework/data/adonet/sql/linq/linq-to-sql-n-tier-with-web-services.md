---
title: "LINQ to SQL-N-Tier mit Webdiensten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9cb10eb8-957f-4beb-a271-5f682016fed2
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# LINQ to SQL-N-Tier mit Webdiensten
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wurde speziell zur Verwendung auf der mittleren Ebene in einer lose verknüpften Datenzugriffsebene \(Data Access Layer, DAL\), z. B. einem Webdienst, entwickelt.  Wenn es sich bei der Präsentationsebene um eine ASP.NET\-Webseite handelt, können Sie die Datenübertragung zwischen der Benutzeroberfläche und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf der mittleren Ebene mithilfe des <xref:System.Web.UI.WebControls.LinqDataSource>\-Webserversteuerelements verwalten.  Wenn es sich bei der Präsentationsebene nicht um eine ASP.NET\-Seite handelt, müssen sowohl die mittlere Ebene als auch die Präsentationsebene zusätzliche Arbeit leisten, um die Serialisierung und Deserialisierung von Daten zu verwalten.  
  
## Einrichten von LINQ to SQL auf der mittleren Ebene  
 In einem Webdienst oder einer N\-Tier\-Anwendung enthält die mittlere Ebene den Datenkontext und die Entitätsklassen.  Sie können diese Klassen manuell erstellen, indem Sie entweder SQLMetal.exe oder [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], wie an anderer Stelle in der Dokumentation beschrieben, verwenden.  Zur Entwurfszeit können Sie die Entitätsklassen serialisierbar machen.  Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md).  Eine weitere Möglichkeit besteht darin, eine separate Gruppe von Klassen zu erstellen, die die zu serialisierenden Daten kapseln, und dann bei der Rückgabe von Daten in den [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]\-Abfragen in diese serialisierbaren Typen zu projizieren.  
  
 Anschließend definieren Sie die Schnittstelle mithilfe der Methoden, die von Clients zum Abrufen, Einfügen und Aktualisieren von Daten aufgerufen werden.  Die Schnittstellenmethoden umschließen die [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]\-Abfragen.  Sie können einen beliebigen Serialisierungsmechanismus verwenden, um Remotemethodenaufrufe und die Serialisierung von Daten zu behandeln.  Wenn Sie in Ihrem Objektmodell über zyklische oder bidirektionale Beziehungen verfügen, z. B. Beziehungen zwischen Customers und Orders im standardmäßigen Northwind\-Objektmodell, besteht die einzige Voraussetzung darin, einen Serialisierer zu verwenden, der das Modell unterstützt.  Die Windows Communication Foundation \(WCF\) <xref:System.Runtime.Serialization.DataContractSerializer> unterstützt im Unterschied zum XmlSerializer, der mit Nicht\-WCF\-Webdiensten verwendet wird, bidirektionale Beziehungen. Wenn Sie den XmlSerializer verwenden möchten, müssen Sie sicherstellen, dass das Objektmodell keine zyklischen Beziehungen aufweist.  
  
 Weitere Informationen zur Windows Communication Foundation finden Sie unter [Windows Communication Foundation Services and WCF Data Services in Visual Studio](../Topic/Windows%20Communication%20Foundation%20Services%20and%20WCF%20Data%20Services%20in%20Visual%20Studio.md).  
  
 Implementieren Sie Geschäftsregeln oder eine andere domänenspezifische Logik, indem Sie die partiellen Klassen und Methoden für<xref:System.Data.Linq.DataContext> und die Entitätsklassen verwenden, um [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Laufzeitereignisse zu verknüpfen.  Weitere Informationen finden Sie unter [Implementieren von N\-Tier\-Geschäftslogik](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md).  
  
## Definieren serialisierbarer Typen  
 Die Client\- oder Präsentationsebene muss über Typdefinitionen für die Klassen verfügen, die Daten von der mittleren Ebene empfangen.  Bei diesen Typen kann es sich um die Entitätsklassen selbst oder um spezielle Klassen handeln, die nur bestimmte Felder aus den Entitätsklassen für das Remoting umschließen.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] braucht sich jedenfalls nicht darum zu kümmern, wie die Präsentationsebene diese Typdefinitionen abruft.  Die Präsentationsebene könnte beispielsweise WCF verwenden, um diese Typen automatisch zu generieren, oder sie könnte eine Kopie der DLL nutzen, in der diese Typen definiert sind. Alternativ könnte sie einfach eigene Versionen dieser Typen definieren.  
  
## Abrufen und Einfügen von Daten  
 Die mittlere Ebene definiert eine Schnittstelle, durch die angegeben wird, wie die Präsentationsebene auf die Daten zugreift.  Beispielsweise `GetProductByID(int productID)` oder `GetCustomers()`.  Auf der mittleren Ebene wird vom Methodentext normalerweise eine neue Instanz von <xref:System.Data.Linq.DataContext> erstellt und eine Abfrage gegen mindestens eine ihrer Tabellen ausgeführt.  Die mittlere Ebene gibt dann das Ergebnis als <xref:System.Collections.Generic.IEnumerable%601> zurück, wobei `T` entweder eine Entitätsklasse oder ein anderer für die Serialisierung verwendeter Typ ist.  Über die Präsentationsebene werden Abfragevariablen nie direkt an die mittlere Ebene gesendet bzw. von ihr empfangen.  Die beiden Ebenen tauschen Werte, Objekte und Auflistungen konkreter Daten aus.  Nachdem eine Auflistung empfangen wurde, kann die Präsentationsebene [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] to Objects verwenden, ums sie ggf. abzufragen.  
  
 Bein Einfügen von Daten kann die Präsentationsebene ein neues Objekt erstellen und es an die mittlere Ebene senden, oder sie kann das Objekt von der mittleren Ebene auf der Grundlage der von ihr gelieferten Daten erstellen lassen.  Im Allgemeinen unterscheidet sich das Abrufen und Einfügen von Daten in N\-Tier\-Anwendungen nicht von der Vorgehensweise in 2\-Tier\-Anwendungen.  Weitere Informationen finden Sie unter [Abfragen der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md) und [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md).  
  
## Nachverfolgen von Änderungen für Update\- und Löschvorgänge  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt vollständige Parallelität auf der Basis von Timestamps \(auch als RowVersions bezeichnet\) und ursprünglichen Werten.  Wenn die Datenbanktabellen über Timestamps verfügen, ist auf der mittleren oder Präsentationsebene wenig zusätzliche Arbeit für Update\- und Löschvorgänge erforderlich.  Wenn Sie für Überprüfungen auf vollständige Parallelität jedoch Originalwerte verwenden müssen, ist die Präsentationsebene dafür verantwortlich, diese Werte zu verfolgen und sie bei der Ausführung von Updates zurückzusenden.  Dies liegt daran, dass Änderungen, die an Entitäten auf der Präsentationsebene vorgenommen wurden, nicht auf der mittleren Ebene verfolgt werden.  Tatsächlich werden das ursprüngliche Abrufen einer Entität und das endgültig vorgenommene Update normalerweise von zwei vollständig getrennten <xref:System.Data.Linq.DataContext>\-Instanzen ausgeführt.  
  
 Je größer die Anzahl der Änderungen ist, die von der Präsentationsebene vorgenommen werden, desto komplexer ist das Verfolgen dieser Änderungen und das Zurückpacken auf die mittlere Ebene.  Die Implementierung eines Mechanismus zum Kommunizieren von Änderungen liegt vollständig in der Zuständigkeit der Anwendung.  Die einzige Voraussetzung besteht darin, dass die ursprünglichen Werte, die für Überprüfungen auf vollständige Parallelität erforderlich sind, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zur Verfügung gestellt werden müssen.  
  
 Weitere Informationen finden Sie unter [Datenabruf und CUD\-Operationen in N\-Tier\-Anwendungen \(LINQ to SQL\)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md).  
  
## Siehe auch  
 [N\-Tier\- und Remoteanwendungen mit LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)   
 [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/de-de/104cfc3f-7385-47d3-8a51-830dfa791136)