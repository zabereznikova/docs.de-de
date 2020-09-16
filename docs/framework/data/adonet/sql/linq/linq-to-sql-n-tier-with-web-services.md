---
title: N-Schicht-LINQ to SQL mit Webdiensten
ms.date: 03/30/2017
ms.assetid: 9cb10eb8-957f-4beb-a271-5f682016fed2
ms.openlocfilehash: 2a6e7cb177d475802d4516d6a7a91f9f5687eada
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555873"
---
# <a name="linq-to-sql-n-tier-with-web-services"></a>N-Schicht-LINQ to SQL mit Webdiensten
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wurde speziell für die Verwendung auf der mittleren Ebene in einer lose gekoppelten Datenzugriffs Schicht (DAL), z. b. einem Webdienst, entwickelt. Wenn es sich bei der Präsentationsebene um eine ASP.NET-Webseite handelt, können Sie die Datenübertragung zwischen der Benutzeroberfläche und <xref:System.Web.UI.WebControls.LinqDataSource> auf der mittleren Ebene mithilfe des [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Webserversteuerelements verwalten. Wenn es sich bei der Präsentationsebene nicht um eine ASP.NET-Seite handelt, müssen sowohl die mittlere Ebene als auch die Präsentationsebene zusätzliche Arbeit leisten, um die Serialisierung und Deserialisierung von Daten zu verwalten.  
  
## <a name="setting-up-linq-to-sql-on-the-middle-tier"></a>Einrichten von LINQ to SQL auf der mittleren Ebene  
 In einem Webdienst oder einer N-Tier-Anwendung enthält die mittlere Ebene den Datenkontext und die Entitätsklassen. Sie können diese Klassen manuell erstellen oder entweder mithilfe von SQLMetal.exe oder der objektrelationaler Designer, wie an anderer Stelle in der-Dokumentation beschrieben. Zur Entwurfszeit können Sie die Entitätsklassen serialisierbar machen. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen von serialisierbaren Entitäten](how-to-make-entities-serializable.md). Eine andere Möglichkeit besteht darin, einen separaten Satz von Klassen zu erstellen, die die zu serialisierenden Daten Kapseln, und dann in diese serialisierbaren Typen zu projizieren, wenn Sie Daten in den LINQ-Abfragen zurückgeben.  
  
 Anschließend definieren Sie die Schnittstelle mithilfe der Methoden, die von Clients zum Abrufen, Einfügen und Aktualisieren von Daten aufgerufen werden. Die Schnittstellen Methoden wrappen Ihre LINQ-Abfragen. Sie können einen beliebigen Serialisierungsmechanismus verwenden, um Remotemethodenaufrufe und die Serialisierung von Daten zu behandeln. Wenn Sie in Ihrem Objektmodell über zyklische oder bidirektionale Beziehungen verfügen, z. B. Beziehungen zwischen Customers und Orders im standardmäßigen Northwind-Objektmodell, besteht die einzige Voraussetzung darin, einen Serialisierer zu verwenden, der das Modell unterstützt. Die Windows Communication Foundation (WCF) <xref:System.Runtime.Serialization.DataContractSerializer> unterstützt im Unterschied zum XmlSerializer, der mit Nicht-WCF-Webdiensten verwendet wird, bidirektionale Beziehungen. Wenn Sie den XmlSerializer verwenden möchten, müssen Sie sicherstellen, dass das Objektmodell keine zyklischen Beziehungen aufweist.  
  
 Weitere Informationen zu Windows Communication Foundation finden Sie unter [Windows Communication Foundation Services und WCF Data Services in Visual Studio](/visualstudio/data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio).  
  
 Implementieren Sie Geschäftsregeln oder eine andere domänenspezifische Logik, indem Sie die partiellen Klassen und Methoden für<xref:System.Data.Linq.DataContext> und die Entitätsklassen verwenden, um [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeitereignisse zu verknüpfen. Weitere Informationen finden Sie unter [Implementieren von N-Tier-Geschäftslogik](implementing-business-logic-linq-to-sql.md).  
  
## <a name="defining-the-serializable-types"></a>Definieren serialisierbarer Typen  
 Die Client- oder Präsentationsebene muss über Typdefinitionen für die Klassen verfügen, die Daten von der mittleren Ebene empfangen. Bei diesen Typen kann es sich um die Entitätsklassen selbst oder um spezielle Klassen handeln, die nur bestimmte Felder aus den Entitätsklassen für das Remoting umschließen. In jedem Fall [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist nicht davon betroffen, wie die Präsentationsebene diese Typdefinitionen abruft. Die Präsentationsebene könnte beispielsweise WCF verwenden, um diese Typen automatisch zu generieren, oder sie könnte eine Kopie der DLL nutzen, in der diese Typen definiert sind. Alternativ könnte sie einfach eigene Versionen dieser Typen definieren.  
  
## <a name="retrieving-and-inserting-data"></a>Abrufen und Einfügen von Daten  
 Die mittlere Ebene definiert eine Schnittstelle, durch die angegeben wird, wie die Präsentationsebene auf die Daten zugreift. Beispiel: `GetProductByID(int productID)` oder `GetCustomers()`. Auf der mittleren Ebene wird vom Methodentext normalerweise eine neue Instanz von <xref:System.Data.Linq.DataContext> erstellt und eine Abfrage gegen mindestens eine ihrer Tabellen ausgeführt. Die mittlere Ebene gibt dann das Ergebnis als <xref:System.Collections.Generic.IEnumerable%601> zurück, wobei `T` entweder eine Entitätsklasse oder ein anderer für die Serialisierung verwendeter Typ ist. Über die Präsentationsebene werden Abfragevariablen nie direkt an die mittlere Ebene gesendet bzw. von ihr empfangen. Die beiden Ebenen tauschen Werte, Objekte und Auflistungen konkreter Daten aus. Nachdem eine Sammlung empfangen wurde, kann die Präsentationsebene LINQ to Objects verwenden, um Sie bei Bedarf abzufragen.  
  
 Bein Einfügen von Daten kann die Präsentationsebene ein neues Objekt erstellen und es an die mittlere Ebene senden, oder sie kann das Objekt von der mittleren Ebene auf der Grundlage der von ihr gelieferten Daten erstellen lassen. Im Allgemeinen unterscheidet sich das Abrufen und Einfügen von Daten in N-Tier-Anwendungen nicht von der Vorgehensweise in 2-Tier-Anwendungen. Weitere Informationen finden Sie unter [Abfragen der Datenbank](querying-the-database.md) und erstellen und Übermitteln von [Datenänderungen](making-and-submitting-data-changes.md).  
  
## <a name="tracking-changes-for-updates-and-deletes"></a>Nachverfolgen von Änderungen für Update- und Löschvorgänge  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt vollständige Parallelität auf der Basis von Timestamps (auch als RowVersions bezeichnet) und ursprünglichen Werten. Wenn die Datenbanktabellen über Timestamps verfügen, ist auf der mittleren oder Präsentationsebene wenig zusätzliche Arbeit für Update- und Löschvorgänge erforderlich. Wenn Sie für Überprüfungen auf vollständige Parallelität jedoch Originalwerte verwenden müssen, ist die Präsentationsebene dafür verantwortlich, diese Werte zu verfolgen und sie bei der Ausführung von Updates zurückzusenden. Dies liegt daran, dass Änderungen, die an Entitäten auf der Präsentationsebene vorgenommen wurden, nicht auf der mittleren Ebene verfolgt werden. Tatsächlich werden das ursprüngliche Abrufen einer Entität und das endgültig vorgenommene Update normalerweise von zwei vollständig getrennten <xref:System.Data.Linq.DataContext>-Instanzen ausgeführt.  
  
 Je größer die Anzahl der Änderungen ist, die von der Präsentationsebene vorgenommen werden, desto komplexer ist das Verfolgen dieser Änderungen und das Zurückpacken auf die mittlere Ebene. Die Implementierung eines Mechanismus zum Kommunizieren von Änderungen liegt vollständig in der Zuständigkeit der Anwendung. Die einzige Anforderung besteht darin, dass die ursprünglichen Werte, die für Überprüfungen auf vollständige Parallelität erforderlich sind, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zur Verfügung gestellt werden müssen.  
  
 Weitere Informationen finden Sie unter [Datenabruf-und CUD-Vorgänge in N-Tier-Anwendungen (LINQ to SQL)](data-retrieval-and-cud-operations-in-n-tier-applications.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [N-Tier-und Remote Anwendungen mit LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
- [Übersicht über das LinqDataSource-Webserver Steuerelement](/previous-versions/aspnet/bb547113(v=vs.100))
