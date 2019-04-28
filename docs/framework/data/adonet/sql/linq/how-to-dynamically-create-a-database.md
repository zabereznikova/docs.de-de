---
title: 'Vorgehensweise: Dynamisches Erstellen einer neuen Datenbank'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb7f23c4-4572-4c38-9898-a287807d070c
ms.openlocfilehash: ab5e2867ce85fcc82e1114696c129aae878bbee6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877265"
---
# <a name="how-to-dynamically-create-a-database"></a>Vorgehensweise: Dynamisches Erstellen einer neuen Datenbank
In LINQ to SQL wird einer relationalen Datenbank ein Objektmodell zugeordnet. Das Mapping wird durch attributbasiertes Mapping oder eine externe Mappingdatei zur Beschreibung der Struktur der relationalen Datenbank ermöglicht. In beiden Szenarien sind genügend Informationen über die relationale Datenbank vorhanden, dass mithilfe der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode eine neue Instanz der Datenbank erstellt werden kann.  
  
 Die <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode erstellt nur in dem Umfang ein Replikat der Datenbank, in dem Informationen im Objektmodell codiert sind. Mappingdateien und -attribute aus dem Objektmodell können möglicherweise nicht alle Informationen zur Struktur einer vorhandenen Datenbank codieren. Mappinginformationen stellen nicht den Inhalt von benutzerdefinierten Funktionen, gespeicherten Prozeduren, Triggern und CHECK-Einschränkungen dar. Dieses Verhalten ist für eine Vielzahl von Datenbanken ausreichend.  
  
 Die <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode kann in einer Vielzahl von Szenarien verwendet werden, insbesondere dann, wenn ein bekannter Datenanbieter wie Microsoft SQL Server 2008 verfügbar ist. Zu den typischen Szenarien zählen:  
  
- Sie erstellen eine Anwendung, die sich automatisch auf einem Kundensystem installiert.  
  
- Sie erstellen eine Clientanwendung, die eine lokale Datenbank benötigt, um den Offlinezustand zu speichern.  
  
 Sie können die <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode auch in Verbindung mit SQL Server nutzen, indem Sie (je nach Verbindungszeichenfolge) eine MDF-Datei oder einen Katalognamen verwenden. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definiert mithilfe der Verbindungszeichenfolge die zu erstellende Datenbank und den zu verwendenden Server.  
  
> [!NOTE]
>  Falls möglich, sollte die integrierte Sicherheit von Windows für die Verbindung mit der Datenbank verwendet werden, sodass in der Verbindungszeichenfolge keine Kennwörter erforderlich sind.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code bietet ein Beispiel für die Erstellung einer neuen Datenbank mit dem Namen "MyDVDs.mdf".  
  
 [!code-csharp[DLinqSubmittingChanges#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#5)]
 [!code-vb[DLinqSubmittingChanges#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#5)]  
  
## <a name="example"></a>Beispiel  
 Das Objektmodell kann verwendet werden, um wie folgt eine Datenbank zu erstellen:  
  
 [!code-csharp[DLinqSubmittingChanges#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#6)]
 [!code-vb[DLinqSubmittingChanges#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#6)]  
  
## <a name="example"></a>Beispiel  
 Beim Erstellen einer Anwendung, die auf einem Kundensystem automatisch installiert wird, sollte überprüft werden, ob die Datenbank bereits existiert. In diesem Fall sollte sie vor der Erstellung einer neuen Datenbank gelöscht werden. Die <xref:System.Data.Linq.DataContext>-Klasse stellt die <xref:System.Data.Linq.DataContext.DatabaseExists%2A>-Methode und die <xref:System.Data.Linq.DataContext.DeleteDatabase%2A>-Methode bereit, um diesen Prozess zu vereinfachen.  
  
 Im folgenden Beispiel wird eine Möglichkeit dargestellt, wie diese Methoden verwendet werden können, um diesen Ansatz zu implementieren:  
  
 [!code-csharp[DLinqSubmittingChanges#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#7)]
 [!code-vb[DLinqSubmittingChanges#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- [External Mapping (Externe Zuordnung)](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
- [SQL-CLR-Typenzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
