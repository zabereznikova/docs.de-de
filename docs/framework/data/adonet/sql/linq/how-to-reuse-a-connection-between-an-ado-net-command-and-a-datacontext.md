---
title: 'Vorgehensweise: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: f1ee7726042327eae88e69e9e6d062909c5bc74e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793290"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Vorgehensweise: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem DataContext
Da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ein Teil der ADO.NET-Technologie ist und auf Diensten basiert, die von ADO.NET bereitgestellt werden, können Sie eine Verbindung zwischen einem ADO.net-Befehl und <xref:System.Data.Linq.DataContext>einem wieder verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die gleiche Verbindung zwischen einem ADO.net-Befehl und <xref:System.Data.Linq.DataContext>der wieder verwendet wird.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch

- [Hintergrundinformationen](background-information.md)
- [ADO.NET und LINQ to SQL](ado-net-and-linq-to-sql.md)
- [Kommunizieren mit der Datenbank](communicating-with-the-database.md)
