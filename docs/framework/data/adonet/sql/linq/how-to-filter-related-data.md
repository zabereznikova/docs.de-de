---
title: 'Vorgehensweise: Filtern von verbundenen Daten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: e12bab55b03fac3383b98b8ee1c56ab1954ff978
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173457"
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="80f77-102">Vorgehensweise: Filtern von verbundenen Daten</span><span class="sxs-lookup"><span data-stu-id="80f77-102">How to: Filter Related Data</span></span>

<span data-ttu-id="80f77-103">Verwenden Sie die <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>-Methode, um Unterabfragen zur Einschränkung der abgerufenen Datenmenge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="80f77-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80f77-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80f77-104">Example</span></span>  

 <span data-ttu-id="80f77-105">Im folgenden Beispiel werden mit der <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>-Methode nur die `Orders` abgerufen, die nicht an diesem Tag versendet wurden.</span><span class="sxs-lookup"><span data-stu-id="80f77-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="80f77-106">Ohne diesen Ansatz werden alle `Orders` abgerufen, auch wenn nur ein Untersatz benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="80f77-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="80f77-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80f77-107">See also</span></span>

- [<span data-ttu-id="80f77-108">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="80f77-108">Querying the Database</span></span>](querying-the-database.md)
