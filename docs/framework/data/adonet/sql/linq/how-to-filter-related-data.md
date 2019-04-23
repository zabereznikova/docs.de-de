---
title: 'Vorgehensweise: Filtern von verbundenen Daten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: 3dbedfb7065ac4b1a570a3f6cdbcdcc2177f20cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218224"
---
# <a name="how-to-filter-related-data"></a>Vorgehensweise: Filtern von verbundenen Daten
Verwenden Sie die <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>-Methode, um Unterabfragen zur Einschränkung der abgerufenen Datenmenge anzugeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden mit der <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>-Methode nur die `Orders` abgerufen, die nicht an diesem Tag versendet wurden. Ohne diesen Ansatz werden alle `Orders` abgerufen, auch wenn nur ein Untersatz benötigt wird.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragen der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
