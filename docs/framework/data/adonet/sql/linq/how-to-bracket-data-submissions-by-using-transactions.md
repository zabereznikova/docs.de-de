---
title: 'Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 6a4c5ba7c4938b48fe489e43ff4a3ff806bd8916
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793804"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Vorgehensweise: Einklammern von Datenübergaben mithilfe von Transaktionen
Sie können <xref:System.Transactions.TransactionScope> verwenden, um die Übergaben zur Datenbank einzuklammern. Weitere Informationen finden Sie [unter Transaktionsunterstützung](transaction-support.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird die Datenbankübergabe in einem <xref:System.Transactions.TransactionScope> eingeschlossen.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](downloading-sample-databases.md)
- [Vornehmen und Übergeben von Datenänderungen](making-and-submitting-data-changes.md)
- [Transaktionsunterstützung](transaction-support.md)
