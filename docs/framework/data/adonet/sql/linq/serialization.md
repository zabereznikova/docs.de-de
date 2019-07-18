---
title: Serialization2
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a15ae411-8dc2-4ca3-84d2-01c9d5f1972a
ms.openlocfilehash: 1ff6f8b58e01c86ae1c1e2e1533b1997ba2eb6b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742887"
---
# <a name="serialization"></a>Serialisierung
In diesem Thema wird beschrieben, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Serialisierungsfunktionen. Die folgenden Abschnitte enthalten Informationen zum Hinzufügen von Serialisierung während der Codeerstellung zur Entwicklungszeit sowie zum Serialisierungsverhalten von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Klassen zur Laufzeit.  
  
 Sie können zur Entwurfszeit durch eine der folgenden Methoden Serialisierungscode hinzufügen:  
  
- Ändern Sie in der Object Relational Designer die **Serialisierungsmodus** Eigenschaft **Unidirectional**.  
  
- Fügen Sie in der SQLMetal-Befehlszeile, die **/serialization** Option. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Übersicht  
 Vom generierten Code [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] stellt die Möglichkeit zum verzögerten Laden standardmäßig bereit. Verzögertes Laden ist auf der Mittelebene eine komfortable Möglichkeit zum transparenten, bedarfsorientierten Laden der Daten. Bei der Serialisierung kommt es jedoch zu Problemen, da hierbei das verzögerte Laden auch dann ausgelöst wird, wenn dieses nicht beabsichtigt ist. Wird ein Objekt serialisiert, wird sein transitiver Abschluss unter allen ausgehenden verzögert geladenen Verweisen serialisiert.  
  
 Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Serialisierungsfunktion behebt dieses Problem in erster Linie durch zwei Mechanismen:  
  
- Ein <xref:System.Data.Linq.DataContext>-Modus für die Deaktivierung des verzögerten Ladens (<xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>). Weitere Informationen finden Sie unter <xref:System.Data.Linq.DataContext>.  
  
- Ein Codegenerierungsschalter zum Erzeugen des <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>-Attributs und des <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=nameWithType>-Attributs für erzeugte Entitäten. Dieser Aspekt, einschließlich des Verhaltens von Klassen zum verzögerten Laden im Rahmen der Serialisierung, ist das Hauptthema dieses Abschnitts.  
  
### <a name="definitions"></a>Definitionen  
  
- *DataContract-Serialisierungsprogramm*: Standard-Serializer, die von der Windows Communication Framework (WCF)-Komponente des .NET Framework 3.0 oder höher.  
  
- *Unidirektionale Serialisierung*: Die serialisierte Version einer Klasse, die nur eine Einweg-Zuordnungseigenschaft (um einen Zyklus zu vermeiden) enthält. Laut Konvention wird die Eigenschaft auf der übergeordneten Seite einer primären Fremdschlüsselbeziehung für die Serialisierung markiert. Die andere Seite in einer bidirektionalen Zuordnung wird nicht serialisiert.  
  
     Unidirektionale Serialisierung ist der einzige Serialisierungstyp, der von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt wird.  
  
## <a name="code-example"></a>Codebeispiel  
 Im folgenden Beispiel werden die herkömmlichen Klassen `Customer` und `Order` aus der Beispieldatenbank Northwind verwendet. Es wird gezeigt, wie diese Klassen mit Serialisierungsattributen versehen werden.  
  
 [!code-csharp[DLinqSerialization#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#1)]
 [!code-vb[DLinqSerialization#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#1)]  
  
 [!code-csharp[DLinqSerialization#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#2)]
 [!code-vb[DLinqSerialization#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#2)]  
  
 [!code-csharp[DLinqSerialization#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#3)]
 [!code-vb[DLinqSerialization#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#3)]  
  
 Für die `Order`-Klasse im folgenden Beispiel wird aus Gründen der Übersicht nur die umgekehrte Zuordnungseigenschaft entsprechend der `Customer`-Klasse dargestellt. Das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut zur Vermeidung eines Zyklus fehlt.  
  
 [!code-csharp[DLinqSerialization#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#4)]
 [!code-vb[DLinqSerialization#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#4)]  
  
 [!code-csharp[DLinqSerialization#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#5)]
 [!code-vb[DLinqSerialization#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#5)]  
  
### <a name="how-to-serialize-the-entities"></a>So serialisieren Sie die Entitäten  
 Sie können die Entitäten im Code im vorherigen Abschnitt wie folgt serialisieren:  
  
 [!code-csharp[DLinqSerialization#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/Program.cs#6)]
 [!code-vb[DLinqSerialization#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/Module1.vb#6)]  
  
### <a name="self-recursive-relationships"></a>Selbstrekursive Beziehungen  
 Selbstrekursive Beziehungen folgen dem gleichen Muster. Die dem Fremdschlüssel entsprechende Zuordnungseigenschaft weist im Gegensatz zur übergeordneten Eigenschaft kein <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf.  
  
 Beachten Sie die folgende Klasse, die über zwei Selbstrekursive Beziehungen verfügt: Employee.Manager/Reports und Employee.Mentor/mentees.  
  
 [!code-csharp[DLinqSerialization#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#7)]
 [!code-vb[DLinqSerialization#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
- [Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)
