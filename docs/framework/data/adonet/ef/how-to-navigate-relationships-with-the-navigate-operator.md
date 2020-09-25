---
title: 'Vorgehensweise: Navigieren in Beziehungen mit dem Navigate-Operator'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: 7d0dbb590555f3e525cd328e4f4b0ad3584f108b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198248"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a>Vorgehensweise: Navigieren in Beziehungen mit dem Navigate-Operator

In diesem Thema wird dargestellt, wie ein Befehl für ein konzeptionelles Modell unter Verwendung eines <xref:System.Data.EntityClient.EntityCommand>-Objekts ausgeführt wird, und wie die <xref:System.Data.Metadata.Edm.RefType>-Ergebnisse mithilfe von <xref:System.Data.EntityClient.EntityDataReader> abgerufen werden.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1. Fügen Sie das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt hinzu, und konfigurieren Sie das Projekt für die Verwendung der Entity Framework. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden des Entity Data Model-Assistenten](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
2. Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie Sie mit [!INCLUDE[esql](../../../../../includes/esql-md.md)] dem [Navigate](./language-reference/navigate-entity-sql.md) -Operator in Beziehungen navigieren können. Der- `Navigate` Operator übernimmt die folgenden Parameter: eine Instanz einer Entität, den Beziehungstyp, das Ende der Beziehung und den Anfang der Beziehung. Optional können Sie nur eine Instanz einer Entität und den Beziehungstyp an den `Navigate` Operator übergeben.  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a>Weitere Informationen

- [EntityClient-Anbieter für Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Entity SQL-Sprache](./language-reference/entity-sql-language.md)
