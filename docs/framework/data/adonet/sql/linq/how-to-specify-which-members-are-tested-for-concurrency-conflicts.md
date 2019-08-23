---
title: 'Vorgehensweise: Angeben, welche Member auf Parallelitätskonflikte getestet werden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
ms.openlocfilehash: fc6fafa474805c2644bb2deabdceed192776ac76
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938754"
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a><span data-ttu-id="5fb2f-102">Vorgehensweise: Angeben, welche Member auf Parallelitätskonflikte getestet werden</span><span class="sxs-lookup"><span data-stu-id="5fb2f-102">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>
<span data-ttu-id="5fb2f-103">Wenden Sie eine von drei Enumerationselementen auf [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die <xref:System.Data.Linq.Mapping.ColumnAttribute> <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> -Eigenschaft eines-Attributs an, um anzugeben, welche Member in Update Überprüfungen zur Erkennung von Konflikten bei der vollständigen Parallelität eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-103">Apply one of three enums to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify which members are to be included in update checks for the detection of optimistic concurrency conflicts.</span></span>  
  
 <span data-ttu-id="5fb2f-104">Die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft (zugeordnet zur Entwurfszeit) wird zusammen mit Funktionen für Laufzeitparallelität in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-104">The <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property (mapped at design time) is used together with run-time concurrency features in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="5fb2f-105">Weitere Informationen finden [Sie unter optimistische Parallelität: Übersicht](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5fb2f-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5fb2f-106">Die ursprünglichen Memberwerte werden mit dem aktuellen Datenbankstatus verglichen, sofern kein Member als `IsVersion=true` gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-106">Original member values are compared with the current database state as long as no member is designated as `IsVersion=true`.</span></span> <span data-ttu-id="5fb2f-107">Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 <span data-ttu-id="5fb2f-108">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-108">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="5fb2f-109">So verwenden Sie immer diesen Member zum Erkennen von Konflikten</span><span class="sxs-lookup"><span data-stu-id="5fb2f-109">To always use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="5fb2f-110">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-110">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="5fb2f-111">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaftswert auf `Always` fest.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-111">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Always`.</span></span>  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="5fb2f-112">So verwenden Sie niemals diesen Member zum Erkennen von Konflikten</span><span class="sxs-lookup"><span data-stu-id="5fb2f-112">To never use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="5fb2f-113">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-113">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="5fb2f-114">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaftswert auf `Never` fest.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-114">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Never`.</span></span>  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a><span data-ttu-id="5fb2f-115">So verwenden Sie diesen Member nur dann zum Erkennen von Konflikten, wenn die Anwendung den Memberwert geändert hat</span><span class="sxs-lookup"><span data-stu-id="5fb2f-115">To use this member for detecting conflicts only when the application has changed the value of the member</span></span>  
  
1. <span data-ttu-id="5fb2f-116">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-116">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="5fb2f-117">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaftswert auf `WhenChanged` fest.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-117">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `WhenChanged`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fb2f-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5fb2f-118">Example</span></span>  
 <span data-ttu-id="5fb2f-119">Das folgende Beispiel zeigt, dass diese `HomePage`-Objekte nie während der Updateprüfungen getestet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-119">The following example specifies that `HomePage` objects should never be tested during update checks.</span></span> <span data-ttu-id="5fb2f-120">Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="5fb2f-120">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5fb2f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fb2f-121">See also</span></span>

- [<span data-ttu-id="5fb2f-122">Vorgehensweise: Verwalten von Änderungs Konflikten</span><span class="sxs-lookup"><span data-stu-id="5fb2f-122">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="5fb2f-123">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="5fb2f-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
