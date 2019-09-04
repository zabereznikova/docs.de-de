---
title: 'Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7139d585-4034-4dfa-916f-2120a8b72792
ms.openlocfilehash: 4805a9f959096b87e2ed3e35b02fbd8c04d45fbc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251486"
---
# <a name="how-to-execute-a-query-that-returns-primitivetype-results"></a>Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt
In diesem Thema wird dargestellt, wie ein Befehl für ein konzeptionelles Modell unter Verwendung eines <xref:System.Data.EntityClient.EntityCommand>-Objekts ausgeführt wird, und wie die <xref:System.Data.Metadata.Edm.PrimitiveType>-Ergebnisse mithilfe von <xref:System.Data.EntityClient.EntityDataReader> abgerufen werden.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1. Fügen Sie das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt hinzu, und konfigurieren Sie [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]das Projekt für die Verwendung von. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie den Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))-Assistenten.  
  
2. Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine Abfrage ausgeführt, die ein <xref:System.Data.Metadata.Edm.PrimitiveType>-Ergebnis zurückgibt. Wenn Sie die folgende Abfrage der `ExecutePrimitiveTypeQuery`-Funktion als Argument übergeben, zeigt die Funktion den durchschnittlichen Listenpreis aller `Products` an:  
  
 [!code-csharp[DP EntityServices Concepts 2#EDM_AVG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#edm_avg)]  
  
 Wenn Sie eine parametrisierte Abfrage wie die folgende übergeben, fügen Sie der <xref:System.Data.EntityClient.EntityParameter>-Eigenschaft die <xref:System.Data.EntityClient.EntityCommand.Parameters%2A>-Objekte auf dem <xref:System.Data.EntityClient.EntityCommand>-Objekt hinzu.  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlprimitivetypes)]
 [!code-vb[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlprimitivetypes)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](./language-reference/entity-sql-reference.md)
- [EntityClient-Anbieter für Entity Framework](entityclient-provider-for-the-entity-framework.md)
