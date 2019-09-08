---
title: 'Vorgehensweise: Angeben von Datenbankdatentypen'
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: 09ca8dc6fa440138523bcd2905335a04517dd806
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793275"
---
# <a name="how-to-specify-database-data-types"></a><span data-ttu-id="bf908-102">Vorgehensweise: Angeben von Datenbankdatentypen</span><span class="sxs-lookup"><span data-stu-id="bf908-102">How to: Specify Database Data Types</span></span>
<span data-ttu-id="bf908-103">Verwenden Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> -Eigenschaft <xref:System.Data.Linq.Mapping.ColumnAttribute> für ein-Attribut, um den genauen Text anzugeben, der die Spalte in einer T-SQL-Tabellen Deklaration definiert.</span><span class="sxs-lookup"><span data-stu-id="bf908-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify the exact text that defines the column in a T-SQL table declaration.</span></span>  
  
 <span data-ttu-id="bf908-104">Sie müssen die <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>-Eigenschaft nur dann angeben, wenn Sie planen, <xref:System.Data.Linq.DataContext.CreateDatabase%2A> zur Erstellung einer Datenbankinstanz einzusetzen.</span><span class="sxs-lookup"><span data-stu-id="bf908-104">You must specify the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property only if you plan to use <xref:System.Data.Linq.DataContext.CreateDatabase%2A> to create an instance of the database.</span></span>  
  
 <span data-ttu-id="bf908-105">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf908-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a><span data-ttu-id="bf908-106">So geben Sie Text an, um einen Datentyp in einer T-SQL-Tabelle zu definieren</span><span class="sxs-lookup"><span data-stu-id="bf908-106">To specify text to define a data type in a T-SQL table</span></span>  
  
1. <span data-ttu-id="bf908-107">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="bf908-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="bf908-108">Legen Sie den Wert der <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>-Eigenschaft auf den genauen Text fest, der von T-SQL verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bf908-108">Set the value of the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the exact text that is used by T-SQL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf908-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf908-109">See also</span></span>

- [<span data-ttu-id="bf908-110">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="bf908-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="bf908-111">Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="bf908-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
