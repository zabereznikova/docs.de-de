---
title: 'Vorgehensweise: Abrufen von Memberkonfliktinformationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: fae1513e7a7ead98318d907b220b7510758c9ffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037601"
---
# <a name="how-to-retrieve-member-conflict-information"></a>Vorgehensweise: Abrufen von Memberkonfliktinformationen
Sie können die <xref:System.Data.Linq.MemberChangeConflict>-Klasse verwenden, um Informationen über einzelne kollidierende Member abzurufen. In diesem gleichen Kontext können Sie für jeden Member für eine benutzerdefinierte Behandlung des Konflikts sorgen. Weitere Informationen finden Sie unter [optimistische Parallelität: Übersicht über die](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code wechselt durch die <xref:System.Data.Linq.ObjectChangeConflict>-Objekte. Für jedes Objekt durchläuft er dann die <xref:System.Data.Linq.MemberChangeConflict>-Objekte.  
  
> [!NOTE]
>  Schließen Sie <xref:System.Reflection> ein, um <xref:System.Data.Linq.MemberChangeConflict.Member%2A>-Informationen bereitzustellen.  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
