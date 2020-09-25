---
title: Serialization2
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a15ae411-8dc2-4ca3-84d2-01c9d5f1972a
ms.openlocfilehash: 778cc73575ffc7421854fd89592f1c4eaa284678
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203552"
---
# <a name="serialization"></a>Serialisierung

In diesem Thema werden die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Serialisierungsfunktionen beschrieben. Die folgenden Abschnitte enthalten Informationen zum Hinzufügen von Serialisierung während der Codeerstellung zur Entwicklungszeit sowie zum Serialisierungsverhalten von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Klassen zur Laufzeit.  
  
 Sie können zur Entwurfszeit durch eine der folgenden Methoden Serialisierungscode hinzufügen:  
  
- Ändern Sie im objektrelationaler Designer die Eigenschaft **Serialisierungsmodus** in **unidirektionale**.  
  
- Fügen Sie in der SQLMetal-Befehlszeile die Option **/Serialization** hinzu. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Übersicht  

 Der von generierte Code [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] stellt standardmäßig verzögerte Ladefunktionen bereit. Verzögertes Laden ist auf der Mittelebene eine komfortable Möglichkeit zum transparenten, bedarfsorientierten Laden der Daten. Bei der Serialisierung kommt es jedoch zu Problemen, da hierbei das verzögerte Laden auch dann ausgelöst wird, wenn dieses nicht beabsichtigt ist. Wird ein Objekt serialisiert, wird sein transitiver Abschluss unter allen ausgehenden verzögert geladenen Verweisen serialisiert.  
  
 Das [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Serialisierungsfeature behandelt dieses Problem, primär durch zwei Mechanismen:  
  
- Ein <xref:System.Data.Linq.DataContext>-Modus für die Deaktivierung des verzögerten Ladens (<xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>). Weitere Informationen finden Sie unter <xref:System.Data.Linq.DataContext>.  
  
- Ein Codegenerierungsschalter zum Erzeugen des <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>-Attributs und des <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=nameWithType>-Attributs für erzeugte Entitäten. Dieser Aspekt, einschließlich des Verhaltens von Klassen zum verzögerten Laden im Rahmen der Serialisierung, ist das Hauptthema dieses Abschnitts.  
  
### <a name="definitions"></a>Definitionen  
  
- *DataContract-Serialisierungsprogramm*: das Standardserialisierungsprogramm, das von der Windows Communication Framework (WCF)-Komponente des .NET Framework 3,0 oder höheren Versionen verwendet wird.  
  
- *Unidirektionale Serialisierung*: die serialisierte Version einer Klasse, die nur eine unidirektionale Zuordnungs Eigenschaft enthält (um eine Zyklen zu vermeiden). Laut Konvention wird die Eigenschaft auf der übergeordneten Seite einer primären Fremdschlüsselbeziehung für die Serialisierung markiert. Die andere Seite in einer bidirektionalen Zuordnung wird nicht serialisiert.  
  
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
  
 Beachten Sie die folgende Klasse, die über zwei selbstrekursive Beziehungen verfügt: Employee.Manager/Reports und Employee.Mentor/Mentees.  
  
 [!code-csharp[DLinqSerialization#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#7)]
 [!code-vb[DLinqSerialization#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#7)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hintergrundinformationen](background-information.md)
- [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten](how-to-make-entities-serializable.md)
