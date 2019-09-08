---
title: 'Vorgehensweise: Darstellen von Spalten als Zeitstempel- oder Versionsspalten'
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: ef99e0420b328f94686e08256ecf229000467810
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793504"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="29ce7-102">Vorgehensweise: Darstellen von Spalten als Zeitstempel- oder Versionsspalten</span><span class="sxs-lookup"><span data-stu-id="29ce7-102">How to: Represent Columns as Timestamp or Version Columns</span></span>
<span data-ttu-id="29ce7-103">Verwenden Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> -Eigenschaft <xref:System.Data.Linq.Mapping.ColumnAttribute> des-Attributs, um ein Feld oder eine Eigenschaft anzugeben, das eine Daten Bank Spalte darstellt, die Daten Bank Zeitstempel oder Versionsnummern enthält.</span><span class="sxs-lookup"><span data-stu-id="29ce7-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="29ce7-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="29ce7-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="29ce7-105">So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer Timestamp- oder Versionsspalte</span><span class="sxs-lookup"><span data-stu-id="29ce7-105">To designate a field or property as representing a timestamp or version column</span></span>  
  
1. <span data-ttu-id="29ce7-106">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="29ce7-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="29ce7-107">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaftswert auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="29ce7-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ce7-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29ce7-108">See also</span></span>

- [<span data-ttu-id="29ce7-109">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="29ce7-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="29ce7-110">Vorgehensweise: Geben Sie an, welche Member auf Parallelitäts Konflikte getestet werden.</span><span class="sxs-lookup"><span data-stu-id="29ce7-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [<span data-ttu-id="29ce7-111">Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="29ce7-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
