---
title: 'Vorgehensweise: Angeben, welche Member auf Parallelitätskonflikte getestet werden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
ms.openlocfilehash: a690e95cadad4ed089fe1bb3ba6fea541a57411f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076301"
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a><span data-ttu-id="cbabf-102">Vorgehensweise: Angeben, welche Member auf Parallelitätskonflikte getestet werden</span><span class="sxs-lookup"><span data-stu-id="cbabf-102">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>
<span data-ttu-id="cbabf-103">Weisen Sie eine der drei Enums auf die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> Eigenschaft für eine <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut, um anzugeben, welche Member werden in Update eingeschlossen werden überprüft, für die Erkennung von Konflikte bezüglich vollständiger Parallelität.</span><span class="sxs-lookup"><span data-stu-id="cbabf-103">Apply one of three enums to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify which members are to be included in update checks for the detection of optimistic concurrency conflicts.</span></span>  
  
 <span data-ttu-id="cbabf-104">Die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft (zugeordnet zur Entwurfszeit) wird zusammen mit Funktionen für Laufzeitparallelität in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbabf-104">The <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property (mapped at design time) is used together with run-time concurrency features in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="cbabf-105">Weitere Informationen finden Sie unter [optimistische Parallelität: Übersicht über die](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cbabf-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbabf-106">Die ursprünglichen Memberwerte werden mit dem aktuellen Datenbankstatus verglichen, sofern kein Member als `IsVersion=true` gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="cbabf-106">Original member values are compared with the current database state as long as no member is designated as `IsVersion=true`.</span></span> <span data-ttu-id="cbabf-107">Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="cbabf-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 <span data-ttu-id="cbabf-108">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="cbabf-108">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="cbabf-109">So verwenden Sie immer diesen Member zum Erkennen von Konflikten</span><span class="sxs-lookup"><span data-stu-id="cbabf-109">To always use this member for detecting conflicts</span></span>  
  
1.  <span data-ttu-id="cbabf-110">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="cbabf-110">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="cbabf-111">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaftswert auf `Always` fest.</span><span class="sxs-lookup"><span data-stu-id="cbabf-111">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Always`.</span></span>  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="cbabf-112">So verwenden Sie niemals diesen Member zum Erkennen von Konflikten</span><span class="sxs-lookup"><span data-stu-id="cbabf-112">To never use this member for detecting conflicts</span></span>  
  
1.  <span data-ttu-id="cbabf-113">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="cbabf-113">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="cbabf-114">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaftswert auf `Never` fest.</span><span class="sxs-lookup"><span data-stu-id="cbabf-114">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Never`.</span></span>  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a><span data-ttu-id="cbabf-115">So verwenden Sie diesen Member nur dann zum Erkennen von Konflikten, wenn die Anwendung den Memberwert geändert hat</span><span class="sxs-lookup"><span data-stu-id="cbabf-115">To use this member for detecting conflicts only when the application has changed the value of the member</span></span>  
  
1.  <span data-ttu-id="cbabf-116">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="cbabf-116">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="cbabf-117">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaftswert auf `WhenChanged` fest.</span><span class="sxs-lookup"><span data-stu-id="cbabf-117">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `WhenChanged`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbabf-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbabf-118">Example</span></span>  
 <span data-ttu-id="cbabf-119">Das folgende Beispiel zeigt, dass diese `HomePage`-Objekte nie während der Updateprüfungen getestet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="cbabf-119">The following example specifies that `HomePage` objects should never be tested during update checks.</span></span> <span data-ttu-id="cbabf-120">Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="cbabf-120">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cbabf-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbabf-121">See also</span></span>

- [<span data-ttu-id="cbabf-122">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="cbabf-122">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="cbabf-123">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="cbabf-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
