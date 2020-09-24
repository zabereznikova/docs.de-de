---
title: 'Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 4d3efedbf15be55fa7a9ab235f881f1c97758953
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161359"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen

Sie können <xref:System.Transactions.TransactionScope> verwenden, um die Übergaben zur Datenbank einzuklammern. Weitere Informationen finden Sie [unter Transaktionsunterstützung](transaction-support.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Code wird die Datenbankübergabe in einem <xref:System.Transactions.TransactionScope> eingeschlossen.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Herunterladen von Beispieldatenbanken](downloading-sample-databases.md)
- [Vornehmen und Übergeben von Datenänderungen](making-and-submitting-data-changes.md)
- [Transaktionsunterstützung](transaction-support.md)
