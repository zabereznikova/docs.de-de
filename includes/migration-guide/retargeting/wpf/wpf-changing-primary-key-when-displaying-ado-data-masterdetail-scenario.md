---
ms.openlocfilehash: 35fc4782ebbba33f5fc6668712af9d89d00cafe9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614617"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a><span data-ttu-id="57265-101">Ändern eines Primärschlüssels durch WPF beim Anzeigen von ADO-Daten in einem Master/Detail-Szenario</span><span class="sxs-lookup"><span data-stu-id="57265-101">WPF Changing a primary key when displaying ADO data in a Master/Detail scenario</span></span>

#### <a name="details"></a><span data-ttu-id="57265-102">Details</span><span class="sxs-lookup"><span data-stu-id="57265-102">Details</span></span>

<span data-ttu-id="57265-103">Nehmen Sie an, Sie haben eine ADO-Sammlung von Elementen des Typs `Order` mit einer Beziehung namens &quot;OrderDetails&quot;, durch die diese Sammlung über den Primärschlüssel &quot;OrderID&quot; mit einer Sammlung von Elementen des Typs `Detail` verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="57265-103">Suppose you have an ADO collection of items of type `Order`, with a relation named &quot;OrderDetails&quot; relating it to a collection of items of type `Detail` via the primary key &quot;OrderID&quot;.</span></span> <span data-ttu-id="57265-104">In Ihrer WPF-App können Sie ein Listensteuerelement an die Details für einen bestimmten Auftrag binden:</span><span class="sxs-lookup"><span data-stu-id="57265-104">In your WPF app, you can bind a list control to the details for a given order:</span></span>

```xaml
<ListBox ItemsSource="{Binding Path=OrderDetails}" >
```

<span data-ttu-id="57265-105">Beim DataContext handelt es sich um ein `Order`-Element.</span><span class="sxs-lookup"><span data-stu-id="57265-105">where the DataContext is an `Order`.</span></span> <span data-ttu-id="57265-106">WPF ruft den Wert der Eigenschaft `OrderDetails` ab. Es handelt sich hierbei um eine D-Sammlung aller `Detail`-Elemente, deren `OrderID` der `OrderID` des Masterelements entspricht.</span><span class="sxs-lookup"><span data-stu-id="57265-106">WPF gets the value of the `OrderDetails` property - a collection D of all the `Detail` items whose `OrderID` matches the `OrderID` of the master item.</span></span> <span data-ttu-id="57265-107">Der Behavior Change wird angezeigt, wenn Sie den Primärschlüssel `OrderID` des Masterelements ändern.</span><span class="sxs-lookup"><span data-stu-id="57265-107">The behavior change arises when you change the primary key `OrderID` of the master item.</span></span> <span data-ttu-id="57265-108">ADO ändert automatisch die `OrderID` jedes der betroffenen Datensätze in der Sammlung „Details“ (also diejenigen, die in Sammlung D kopiert wurden).</span><span class="sxs-lookup"><span data-stu-id="57265-108">ADO automatically changes the `OrderID` of each of the affected records in the Details collection (namely the ones copied into collection D).</span></span>  <span data-ttu-id="57265-109">Was passiert mit D?</span><span class="sxs-lookup"><span data-stu-id="57265-109">But what happens to D?</span></span>

- <span data-ttu-id="57265-110">Altes Verhalten: Sammlung D wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="57265-110">Old behavior: Collection D is cleared.</span></span> <span data-ttu-id="57265-111">Das Masterelement löst *keine* Änderungsbenachrichtigung für die Eigenschaft `OrderDetails` aus.</span><span class="sxs-lookup"><span data-stu-id="57265-111">The master item does *not* raise a change notification for property `OrderDetails`.</span></span> <span data-ttu-id="57265-112">Das ListBox-Element verwendet weiterhin Sammlung D, die jetzt leer ist.</span><span class="sxs-lookup"><span data-stu-id="57265-112">The ListBox continues to use collection D, which is now empty.</span></span>
- <span data-ttu-id="57265-113">Neues Verhalten:  Sammlung D wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="57265-113">New behavior:  Collection D is unchanged.</span></span> <span data-ttu-id="57265-114">Jedes enthaltene Element löst Änderungsbenachrichtigung für die Eigenschaft `OrderID` aus.</span><span class="sxs-lookup"><span data-stu-id="57265-114">Each of its items raises a change notification for the `OrderID` property.</span></span> <span data-ttu-id="57265-115">ListBox verwendet weiterhin Sammlung D, und zeigt die Details mit der neuen `OrderID` an.</span><span class="sxs-lookup"><span data-stu-id="57265-115">The ListBox continues to use collection D, and displays the details with the new `OrderID`.</span></span> <span data-ttu-id="57265-116">WPF implementiert das neue Verhalten, indem Sammlung D auf andere Weise erstellt wird: durch Aufruf der ADO-Methode <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> mit dem auf `true` festgelegten `followParent`-Argument.</span><span class="sxs-lookup"><span data-stu-id="57265-116">WPF implements the new behavior by creating collection D in a different way:  by calling the ADO method <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> with the `followParent` argument set to `true`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="57265-117">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="57265-117">Suggestion</span></span>

<span data-ttu-id="57265-118">Eine App ruft das neue Verhalten durch Verwendung der folgenden AppContext-Option auf.</span><span class="sxs-lookup"><span data-stu-id="57265-118">An app gets the new behavior by using the following AppContext switch.</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false"/>
  </runtime>
</configuration>
```

<span data-ttu-id="57265-119">Die Option ist für Apps, die auf .NET 4.7.1 oder niedriger ausgelegt sind, standardmäßig auf `true` festgelegt (altes Verhalten). Für Apps, die auf .NET 4.7.2 oder höher ausgelegt sind, ist sie standardmäßig auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="57265-119">The switch defaults to `true` (old behavior) for apps that target .NET 4.7.1 or below, and to `false` (new behavior) for apps that target .NET 4.7.2 or above.</span></span>

| <span data-ttu-id="57265-120">name</span><span class="sxs-lookup"><span data-stu-id="57265-120">Name</span></span>    | <span data-ttu-id="57265-121">Wert</span><span class="sxs-lookup"><span data-stu-id="57265-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="57265-122">Bereich</span><span class="sxs-lookup"><span data-stu-id="57265-122">Scope</span></span>   | <span data-ttu-id="57265-123">Gering</span><span class="sxs-lookup"><span data-stu-id="57265-123">Minor</span></span>       |
| <span data-ttu-id="57265-124">Version</span><span class="sxs-lookup"><span data-stu-id="57265-124">Version</span></span> | <span data-ttu-id="57265-125">4.7.2</span><span class="sxs-lookup"><span data-stu-id="57265-125">4.7.2</span></span>       |
| <span data-ttu-id="57265-126">Typ</span><span class="sxs-lookup"><span data-stu-id="57265-126">Type</span></span>    | <span data-ttu-id="57265-127">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="57265-127">Retargeting</span></span> |
