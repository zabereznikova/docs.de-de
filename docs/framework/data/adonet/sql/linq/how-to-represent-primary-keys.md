---
title: "Gewusst wie: Darstellen von Primärschlüsseln"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3510d52f6f6de9ee2e99ebc1e9fc6fa581d58f3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="fbb66-102">Gewusst wie: Darstellen von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="fbb66-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="fbb66-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> Eigenschaft auf die <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut um eine Eigenschaft oder ein Feld zur Darstellung des Primärschlüssels für eine Datenbankspalte zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="fbb66-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="fbb66-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="fbb66-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="fbb66-105"> unterstützt keine berechneten Spalten als Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="fbb66-105"> does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="fbb66-106">So legen Sie eine Eigenschaft oder ein Feld als Primärschlüssel fest</span><span class="sxs-lookup"><span data-stu-id="fbb66-106">To designate a property or field as a primary key</span></span>  
  
1.  <span data-ttu-id="fbb66-107">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="fbb66-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="fbb66-108">Geben Sie den Wert als `true` an.</span><span class="sxs-lookup"><span data-stu-id="fbb66-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbb66-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbb66-109">See Also</span></span>  
 [<span data-ttu-id="fbb66-110">Die LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="fbb66-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="fbb66-111">Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code-Editors</span><span class="sxs-lookup"><span data-stu-id="fbb66-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
