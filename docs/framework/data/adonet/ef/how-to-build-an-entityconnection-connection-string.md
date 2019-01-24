---
title: 'Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: a78d325b5a687a09ef1d1e627c5894808538aaa3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632759"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a>Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge
In diesem Thema wird anhand eines Beispiels gezeigt, wie eine <xref:System.Data.EntityClient.EntityConnection> erstellt wird.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1.  Hinzufügen der [AdventureWorks Sales-Modell](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) zu Ihrem Projekt und Konfigurieren Ihres Projekts zur Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> für den zugrunde liegenden Anbieter initialisiert. Anschließend wird das <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType>-Objekt initialisiert und an den Konstruktor der <xref:System.Data.EntityClient.EntityConnection> übergeben.  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Verwenden Sie EntityConnection-Objekt mit einem Objektkontext](https://msdn.microsoft.com/library/2140fe7b-b88b-47c8-a749-d7f142eb1080)
- [EntityClient-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
