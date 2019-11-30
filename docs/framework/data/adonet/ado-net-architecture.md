---
title: ADO.NET-Architektur
ms.date: 03/30/2017
ms.assetid: fcd45b99-ae8f-45ab-8b97-d887beda734e
ms.openlocfilehash: 2692959d5a3e12d503d91b55e19f744bb9abd112
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568461"
---
# <a name="adonet-architecture"></a>ADO.NET-Architektur
Die traditionelle Datenverarbeitung basierte primär auf einem verbindungsbasierten Modell mit zwei Ebenen. Da für die Datenverarbeitung immer mehr auf Architekturen mit mehreren Ebenen zurückgegriffen wird, wird verstärkt mit nicht verbundenen Lösungen gearbeitet, um eine bessere Skalierbarkeit der Anwendungen zu erzielen.  
  
## <a name="adonet-components"></a>ADO.NET-Komponenten  
 Die zwei Hauptkomponenten von ADO.net für den Zugriff auf und die Bearbeitung von Daten sind die .NET Framework-Datenanbieter und die-<xref:System.Data.DataSet>.  
  
### <a name="net-framework-data-providers"></a>.NET Framework-Datenanbieter  
 Die .NET Framework-Datenanbieter sind Komponenten, die explizit für die Datenbearbeitung und den schnellen, vorwärts gerichteten, schreibgeschützten Zugriff auf Daten entworfen wurden. Das `Connection`-Objekt sorgt für die Verbindung mit einer Datenquelle. Mit dem `Command`-Objekt können Sie auf Datenbankbefehle zugreifen, um Daten zurückzugeben oder zu ändern, gespeicherte Prozeduren auszuführen und Parameterinformationen zu senden oder abzurufen. Der `DataReader` sorgt dafür, dass die Daten mit maximaler Geschwindigkeit per Stream bereitgestellt werden. Der `DataAdapter` fungiert als Brücke zwischen dem `DataSet`-Objekt und der Datenquelle. Der `DataAdapter` verwendet zum Ausführen von SQL-Befehlen an der Datenquelle `Command`-Objekte, um damit sowohl Daten in das `DataSet` zu laden als auch um die Datenquelle mit den an den Daten im `DataSet` vorgenommenen Änderungen zu aktualisieren. Weitere Informationen finden Sie unter [.NET Framework-Datenanbietern](data-providers.md) und [Abrufen und Ändern von Daten in ADO.net](retrieving-and-modifying-data.md).  
  
### <a name="the-dataset"></a>Das "DataSet"  
 Das ADO.NET-`DataSet` wurde explizit für den datenquellenunabhängigen Datenzugriff entwickelt. Aus diesem Grund kann es mit mehreren, unterschiedlichen Datenquellen, mit XML-Daten oder zum Verwalten von lokalen Anwendungsdaten verwendet werden. Das `DataSet` enthält eine Auflistung von einem oder mehreren <xref:System.Data.DataTable>-Objekten, die aus Datenzeilen und -spalten sowie aus Primärschlüsseln, Fremdschlüsseln, Einschränkungen und Beziehungsinformationen zu den in den `DataTable`-Objekten enthaltenen Daten bestehen. Weitere Informationen finden Sie unter [Datasets, DataTables und DataViews](./dataset-datatable-dataview/index.md).  
  
 Das folgende Diagramm veranschaulicht die Beziehung zwischen einem .NET Framework Datenanbieter und einem `DataSet`.  
  
 ![ADO.net-Grafik](./media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
ADO.NET-Architektur  
  
### <a name="choosing-a-datareader-or-a-dataset"></a>Auswählen eines "DataReader" oder eines "DataSet"  
 Wenn Sie entscheiden, ob die Anwendung eine `DataReader` verwenden soll (siehe [Abrufen von Daten mit einem DataReader](retrieving-data-using-a-datareader.md)) oder eine `DataSet` (siehe [Datasets, DataTables und DataViews](./dataset-datatable-dataview/index.md)), berücksichtigen Sie den Funktionstyp, den die Anwendung erfordert. Ein `DataSet` sollten Sie für folgende Aufgaben verwenden:  
  
- Lokales Zwischenspeichern von Daten in Ihrer Anwendung, um sie bearbeiten zu können. Wenn die Ergebnisse einer Abfrage nur gelesen werden sollen, ist der `DataReader` die bessere Wahl.  
  
- Verschieben von Daten zwischen Ebenen oder von einem XML-Webdienst.  
  
- Dynamisches Interagieren mit Daten, wie Datenbindung an ein Windows Forms-Steuerelement, oder Kombinieren von und Erstellen einer Beziehung zwischen Daten aus mehreren Quellen.  
  
- Ausführen umfangreicher Datenverarbeitungsschritte ohne eine offene Verbindung zur Datenquelle. Dadurch wird die Verbindung zur Nutzung durch andere Clients freigegeben.  
  
 Wenn Sie die vom `DataSet` bereitgestellte Funktionalität nicht benötigen, können Sie die Geschwindigkeit Ihrer Anwendung verbessern, indem Sie den `DataReader` verwenden, der Ihre Daten vorwärts gerichtet und schreibgeschützt zurückgibt. Obwohl der `DataAdapter` die `DataReader` verwendet, um den Inhalt eines `DataSet` auszufüllen (siehe Auffüllen [eines Datasets von einem DataAdapter](populating-a-dataset-from-a-dataadapter.md)), können Sie die Leistung steigern, indem Sie den `DataReader`verwenden, um die Leistung zu verbessern, da Sie Speicherplatz einsparen, der vom `DataSet`beansprucht wird, und die Verarbeitung vermeiden, die zum Erstellen und Ausfüllen des Inhalts der `DataSet`erforderlich ist.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 LINQ to DataSet stellt Abfragefunktionen und Typüberprüfungsfunktionen zur Kompilierzeit über die in einem DataSet-Objekt zwischengespeicherten Daten bereit. Sie können damit Abfragen in einer der .NET Framework-Entwicklungssprachen schreiben, z. B. in C# oder Visual Basic. Weitere Informationen finden Sie unter [LINQ to DataSet](linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 LINQ to SQL unterstützt Abfragen für ein Objektmodell, das den Datenstrukturen einer relationalen Datenbank zugeordnet ist, ohne dass ein vorläufiges Konzeptmodell verwendet wird. Jede Tabelle wird durch eine separate Klasse dargestellt, wodurch das Objektmodell eng mit dem relationalen Datenbankschema verbunden wird. LINQ to SQL übersetzt im Objektmodell vorhandene LINQ-Abfragen in Transact-SQL und sendet diese zur Ausführung an die Datenbank. Wenn die Datenbank die Ergebnisse zurückgibt, übersetzt LINQ to SQL die Ergebnisse zurück in Objekte. Weitere Informationen finden Sie unter [LINQ to SQL](./sql/linq/index.md).  
  
## <a name="adonet-entity-framework"></a>ADO.NET Entity Framework  
 Das ADO.NET Entity Framework wurde entworfen, um Entwicklern die Möglichkeit zu geben, Anwendungen für den Datenzugriff zu erstellen, indem sie bei der Programmierung auf ein konzeptionelles Anwendungsmodell zugreifen können, anstatt direkt mit einem relationalen Speicherschema zu arbeiten. Das Ziel ist es, die Menge des Codes und den Wartungsaufwand zu verringern, die für datenorientierte Anwendungen erforderlich sind. Weitere Informationen finden Sie unter [ADO.NET Entity Framework](./ef/index.md).  
  
## <a name="wcf-data-services"></a>WCF Data Services  
 WCF Data Services wird verwendet, um Datendienste im Internet oder in einem Intranet bereitzustellen. Die Daten werden gemäß den Spezifikationen des Entity Data Model in Entitäten und Beziehungen strukturiert. Die in diesem Modell bereitgestellten Daten sind durch das Standard-HTTP-Protokoll adressierbar. Weitere Informationen finden Sie unter [WCF Data Services 4.5](../wcf/index.md).  
  
## <a name="xml-and-adonet"></a>XML und ADO.NET  
 ADO.net nutzt die Leistungsfähigkeit von XML, um den getrennten Zugriff auf Daten bereitzustellen. ADO.net wurde Hand in Hand mit den XML-Klassen in der .NET Framework entworfen. Beides sind Komponenten einer einzelnen Architektur.  
  
 ADO.net und die XML-Klassen im-.NET Framework werden im `DataSet` Objekt konvergiert. Das `DataSet` kann mit Daten aus einer XML-Quelle gefüllt werden, gleich, ob es sich dabei um eine Datei oder um einen XML-Stream handelt. Das `DataSet` kann als W3C-konformer XML-Code geschrieben werden, dessen Schema als XSD-Schema (XML Schema Definition Language) ausgeführt ist. Die Quelle der Daten im `DataSet` spielt dabei keine Rolle. Da das systemeigene Serialisierungsformat des `DataSet` XML ist, handelt es sich um ein hervorragendes Medium zum Verschieben von Daten zwischen den Ebenen der Architektur. Somit ist das `DataSet` eine optimale Wahl für das Remoting von Daten und Schemakontext zu und von einem XML-Webdienst. Weitere Informationen hierzu finden Sie unter [XML Documents and Data (XML-Dokumente und -Daten)](../../../standard/data/xml/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](ado-net-overview.md)
