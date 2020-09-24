---
title: 'Vorgehensweise: Erkennen und Auflösen von Übergabekonflikten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 96e96208d9bb28092701164e6cd5943ef81515a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147722"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>Vorgehensweise: Erkennen und Auflösen von Übergabekonflikten

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] stellt viele Ressourcen zur Erkennung und Auflösung von Konflikten bereit, die von Mehrbenutzeränderungen an der Datenbank stammen. Weitere Informationen finden Sie unter Gewusst [wie: Verwalten von Änderungs Konflikten](how-to-manage-change-conflicts.md).  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel zeigt einen- `try` / `catch` Block, der eine-Ausnahme abfängt <xref:System.Data.Linq.ChangeConflictException> . Entitäts- und Memberinformationen für jeden Konflikt werden im Konsolenfenster angezeigt.  
  
> [!NOTE]
> Sie müssen die `using System.Reflection`-Direktive (`Imports System.Reflection` in Visual Basic) einschließen, um das Abrufen von Informationen zu unterstützen. Weitere Informationen finden Sie unter <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Vornehmen und Übergeben von Datenänderungen](making-and-submitting-data-changes.md)
- [Vorgehensweise: Verwalten von Änderungskonflikten](how-to-manage-change-conflicts.md)
