---
title: Konvertieren eines Typs in eine generische "IEnumerable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: c2d34ae708f79d9f920679b3714a100fe8943c38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164414"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a>Konvertieren eines Typs in eine generische "IEnumerable"

Verwenden Sie <xref:System.Linq.Enumerable.AsEnumerable%2A>, um das als generische `IEnumerable` eingegebene Argument zurückzugeben.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel würde [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (mit der generischen Standard-`Query`) versuchen, die Abfrage in SQL zu konvertieren und auf dem Server auszuführen. Die `where`-Klausel verweist jedoch auf eine benutzerdefinierte clientseitige Methode (`isValidProduct`), die nicht in SQL konvertiert werden kann.  
  
 Die Lösung erfordert das Definieren der clientseitigen generischen <xref:System.Collections.Generic.IEnumerable%601>-Implementierung von `where`, um das generische <xref:System.Linq.IQueryable%601> zu ersetzen. Rufen Sie hierzu den <xref:System.Linq.Enumerable.AsEnumerable%2A>-Operator auf.  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfrage Beispiele](query-examples.md)
