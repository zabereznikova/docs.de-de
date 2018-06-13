---
title: 'Gewusst wie: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem "DataContext"'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 9618ffd3f6b1a050a4c47d1912b4612ce4031cd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352947"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Gewusst wie: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem "DataContext"
Da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist ein Teil der [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] Technologiefamilie und basiert auf Dienste von [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], können Sie eine Verbindung zwischen Wiederverwenden einer [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] Befehl und einem <xref:System.Data.Linq.DataContext>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die gleiche Verbindung zwischen einem [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]-Befehl und dem <xref:System.Data.Linq.DataContext> wiederverwendet wird.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [ADO.NET und LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [Kommunizieren mit der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
