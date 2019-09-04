---
title: 'Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: 33a52b2542a2e312f7fbb8b7ca09a8b85662d2d4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251551"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a>Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge
In diesem Thema wird anhand eines Beispiels gezeigt, wie eine <xref:System.Data.EntityClient.EntityConnection> erstellt wird.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1. Fügen Sie das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt hinzu, und konfigurieren Sie [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]das Projekt für die Verwendung von. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie den Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))-Assistenten.  
  
2. Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> für den zugrunde liegenden Anbieter initialisiert. Anschließend wird das <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType>-Objekt initialisiert und an den Konstruktor der <xref:System.Data.EntityClient.EntityConnection> übergeben.  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwenden von EntityConnection mit einem Objekt Kontext](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))
- [EntityClient-Anbieter für Entity Framework](entityclient-provider-for-the-entity-framework.md)
