---
title: 'Vorgehensweise: Erkennen und Auflösen von Übergabekonflikten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: ff33196f83e2c0d8d759e4ffc3fb7442e8ba0e3b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940097"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>Vorgehensweise: Erkennen und Auflösen von Übergabekonflikten
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] stellt viele Ressourcen zur Erkennung und Auflösung von Konflikten bereit, die von Mehrbenutzeränderungen an der Datenbank stammen. Weitere Informationen finden Sie unter [Vorgehensweise: Verwalten von Änderungs](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)Konflikten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen `try` / `catch` -Block, der <xref:System.Data.Linq.ChangeConflictException> eine-Ausnahme abfängt. Entitäts- und Memberinformationen für jeden Konflikt werden im Konsolenfenster angezeigt.  
  
> [!NOTE]
> Sie müssen die `using System.Reflection`-Direktive (`Imports System.Reflection` in Visual Basic) einschließen, um das Abrufen von Informationen zu unterstützen. Weitere Informationen finden Sie unter <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [Vorgehensweise: Verwalten von Änderungs Konflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
