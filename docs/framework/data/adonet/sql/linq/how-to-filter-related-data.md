---
title: 'Vorgehensweise: Filtern von verbundenen Daten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: 9a046c94363a1a161e19dcb68e015f8c6791e511
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703470"
---
# <a name="how-to-filter-related-data"></a>Vorgehensweise: Filtern von verbundenen Daten
Verwenden Sie die <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>-Methode, um Unterabfragen zur Einschränkung der abgerufenen Datenmenge anzugeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden mit der <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>-Methode nur die `Orders` abgerufen, die nicht an diesem Tag versendet wurden. Ohne diesen Ansatz werden alle `Orders` abgerufen, auch wenn nur ein Untersatz benötigt wird.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch
- [Abfragen der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
