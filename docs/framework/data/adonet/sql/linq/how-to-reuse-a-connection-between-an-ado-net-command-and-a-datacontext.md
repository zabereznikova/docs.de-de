---
title: 'Vorgehensweise: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 89c9a12399d3d76487d1fdc2bd82aa037c167710
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197351"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Vorgehensweise: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem DataContext

Da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ein Teil der ADO.NET-Technologie ist und auf Diensten basiert, die von ADO.NET bereitgestellt werden, können Sie eine Verbindung zwischen einem ADO.net-Befehl und einem wieder verwenden <xref:System.Data.Linq.DataContext> .  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie die gleiche Verbindung zwischen einem ADO.net-Befehl und der wieder verwendet wird <xref:System.Data.Linq.DataContext> .  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hintergrundinformationen](background-information.md)
- [ADO.NET und LINQ to SQL](ado-net-and-linq-to-sql.md)
- [Kommunizieren mit der Datenbank](communicating-with-the-database.md)
