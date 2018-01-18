---
title: 'Gewusst wie: Darstellen von berechneten Spalten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 76f6d64c6577456d1208d2d157c5560e49f85f7e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="7623b-102">Gewusst wie: Darstellen von berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="7623b-102">How to: Represent Computed Columns</span></span>
<span data-ttu-id="7623b-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> Eigenschaft auf einen <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut für die Darstellung einer Spalteninhalts, deren Inhalt das Ergebnis der Berechnung sind.</span><span class="sxs-lookup"><span data-stu-id="7623b-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="7623b-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="7623b-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="7623b-105"> unterstützt keine berechneten Spalten als Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="7623b-105"> does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="7623b-106">So stellen Sie eine berechnete Spalte dar</span><span class="sxs-lookup"><span data-stu-id="7623b-106">To represent a computed column</span></span>  
  
1.  <span data-ttu-id="7623b-107">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="7623b-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="7623b-108">Weisen Sie der <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>-Eigenschaft eine Zeichenfolgendarstellung der Formel zu.</span><span class="sxs-lookup"><span data-stu-id="7623b-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7623b-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7623b-109">See Also</span></span>  
 [<span data-ttu-id="7623b-110">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="7623b-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="7623b-111">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="7623b-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
