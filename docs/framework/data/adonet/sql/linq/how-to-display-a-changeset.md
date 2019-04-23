---
title: 'Vorgehensweise: Anzeigen eines ChangeSet-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: 92acee0d36634ea09c245418fcc7a8b97d208aa6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228630"
---
# <a name="how-to-display-a-changeset"></a>Vorgehensweise: Anzeigen eines ChangeSet-Objekts
Sie können die von einem <xref:System.Data.Linq.DataContext> verfolgten Änderungen mithilfe von <xref:System.Data.Linq.DataContext.GetChangeSet%2A> anzeigen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Kunden aus London abgerufen, der Ort wird in Paris geändert, und die Änderungen werden wieder an die Datenbank übergeben.  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 Die Ausgabe dieses Codes ähnelt der folgenden. Beachten Sie, dass die Zusammenfassung am Ende zeigt, dass acht Änderungen vorgenommen wurden.  

 ```console
CustomerID: AROUT
   Original value: London
   Updated value: Paris
CustomerID: BSBEV
   Original value: London
   Updated value: Paris
CustomerID: CONSH
   Original value: London
   Updated value: Paris
CustomerID: EASTC
   Original value: London
   Updated value: Paris
CustomerID: NORTS
    Original value: London
    Updated value: Paris
CustomerID: PARIS
    Original value: London
    Updated value: Paris
CustomerID: SEVES
    Original value: London
    Updated value: Paris
CustomerID: SPECD
    Original value: London
    Updated value: Paris
Total changes: {Added: 0, Removed: 0, Modified: 8}
```
  
## <a name="see-also"></a>Siehe auch

- [Debugunterstützung](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
