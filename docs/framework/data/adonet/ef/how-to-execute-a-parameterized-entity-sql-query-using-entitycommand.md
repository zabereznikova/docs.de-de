---
title: 'Vorgehensweise: Ausführen einer parametrisierten Entity SQL-Abfrage mithilfe von „EntityCommand“'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: addda1a18ab325971b823d0131338a7bb824ad5c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251529"
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a>Vorgehensweise: Ausführen einer parametrisierten Entity SQL-Abfrage mithilfe von „EntityCommand“
In diesem Thema wird gezeigt, wie [!INCLUDE[esql](../../../../../includes/esql-md.md)] eine Abfrage mit Parametern mithilfe eines <xref:System.Data.EntityClient.EntityCommand> -Objekts ausgeführt wird.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1. Fügen Sie das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt hinzu, und konfigurieren Sie [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]das Projekt für die Verwendung von. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie den Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))-Assistenten.  
  
2. Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie eine Abfragezeichenfolge mit zwei Parametern konstruiert wird. Zunächst wird ein <xref:System.Data.EntityClient.EntityCommand> erstellt, dann werden der <xref:System.Data.EntityClient.EntityParameter>-Auflistung dieses <xref:System.Data.EntityClient.EntityCommand> zwei Parameter hinzugefügt, und schließlich wird die Auflistung der `Contact`-Elemente durchlaufen.  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Ausführen einer parametrisierten Abfrage](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))
- [Entity SQL Language (Entity SQL-Sprache)](./language-reference/entity-sql-language.md)
