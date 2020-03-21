---
title: Erforderliche Argumente und Überladungsgruppen
ms.date: 03/30/2017
ms.assetid: 4ca3ed06-b9af-4b85-8b70-88c2186aefa3
ms.openlocfilehash: 4eb62306f52b8ff890d5a5333c3789bd84ad7f60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142939"
---
# <a name="required-arguments-and-overload-groups"></a><span data-ttu-id="43954-102">Erforderliche Argumente und Überladungsgruppen</span><span class="sxs-lookup"><span data-stu-id="43954-102">Required Arguments and Overload Groups</span></span>
<span data-ttu-id="43954-103">Aktivitäten können so konfiguriert werden, dass bestimmte Argumente gebunden werden müssen, wenn die Ausführung der Aktivität gültig sein soll.</span><span class="sxs-lookup"><span data-stu-id="43954-103">Activities can be configured so that certain arguments are required to be bound for the activity to be valid for execution.</span></span> <span data-ttu-id="43954-104">Das `RequiredArgument`-Attribut wird verwendet, um anzugeben, dass bestimmte Argumente für eine Aktivität erforderlich sind. Mit dem `OverloadGroup`-Attribut werden die Kategorien erforderlicher Argumente zusammen anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="43954-104">The `RequiredArgument` attribute is used to indicate that certain arguments on an activity are required and the `OverloadGroup` attribute is used to group categories of required arguments together.</span></span> <span data-ttu-id="43954-105">Mit diesen Attributen können Aktivitätsautoren einfache oder komplexe Konfigurationen für die Aktivitätsvalidierung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="43954-105">By using the attributes, activity authors can provide simple or complex activity validation configurations.</span></span>  
  
## <a name="using-required-arguments"></a><span data-ttu-id="43954-106">Verwenden von erforderlichen Argumenten</span><span class="sxs-lookup"><span data-stu-id="43954-106">Using Required Arguments</span></span>  
 <span data-ttu-id="43954-107">Damit das `RequiredArgument`-Attribut in einer Aktivität verwendet werden kann, geben Sie die gewünschten Argumente mit <xref:System.Activities.RequiredArgumentAttribute> an.</span><span class="sxs-lookup"><span data-stu-id="43954-107">To use the `RequiredArgument` attribute in an activity, indicate the desired arguments using <xref:System.Activities.RequiredArgumentAttribute>.</span></span> <span data-ttu-id="43954-108">In diesem Beispiel wird eine `Add`-Aktivität definiert, die über zwei erforderliche Argumente verfügt.</span><span class="sxs-lookup"><span data-stu-id="43954-108">In this example, an `Add` activity is defined that has two required arguments.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="43954-109">In XAML werden erforderliche Argumente auch durch die Verwendung des <xref:System.Activities.RequiredArgumentAttribute>-Objekts angegeben.</span><span class="sxs-lookup"><span data-stu-id="43954-109">In XAML, required arguments are also indicated by using <xref:System.Activities.RequiredArgumentAttribute>.</span></span> <span data-ttu-id="43954-110">In diesem Beispiel wird die `Add`-Aktivität unter Verwendung von drei Argumenten definiert. Sie verwendet eine <xref:System.Activities.Statements.Assign%601>-Aktivität, um den Hinzufügevorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="43954-110">In this example the `Add` activity is defined by using three arguments and uses an <xref:System.Activities.Statements.Assign%601> activity to perform the add operation.</span></span>  
  
```xaml  
<Activity x:Class="ValidationDemo.Add" ...>  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)">  
      <x:Property.Attributes>  
        <RequiredArgumentAttribute />  
      </x:Property.Attributes>  
    </x:Property>  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)">  
      <x:Property.Attributes>  
        <RequiredArgumentAttribute />  
      </x:Property.Attributes>  
    </x:Property>  
    <x:Property Name="Result" Type="OutArgument(x:Int32)" />  
  </x:Members>  
  <Assign>  
    <Assign.To>  
      <OutArgument x:TypeArguments="x:Int32">[Result]</OutArgument>  
    </Assign.To>  
    <Assign.Value>  
      <InArgument x:TypeArguments="x:Int32">[Operand1 + Operand2]</InArgument>  
    </Assign.Value>  
  </Assign>  
</Activity>  
```  
  
 <span data-ttu-id="43954-111">Wenn die Aktivität verwendet wird und eines der beiden erforderlichen Argumente nicht gebunden ist, wird der folgende Validierungsfehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="43954-111">If the activity is used and either of the required arguments is not bound the following validation error is returned.</span></span>  
  
 <span data-ttu-id="43954-112">**Für das erforderliche Aktivitätsargument 'Operand1' wurde kein Wert angegeben.**</span><span class="sxs-lookup"><span data-stu-id="43954-112">**Value for a required activity argument 'Operand1' was not supplied.**</span></span>  
> [!NOTE]
> <span data-ttu-id="43954-113">Weitere Informationen zum Überprüfen und Behandeln von Validierungsfehlern und Warnungen finden Sie unter [Aufrufen von Aktivitätsvalidierung](invoking-activity-validation.md).</span><span class="sxs-lookup"><span data-stu-id="43954-113">For more information about checking for and handling validation errors and warnings, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>  
  
## <a name="using-overload-groups"></a><span data-ttu-id="43954-114">Verwenden von Überladungsgruppen</span><span class="sxs-lookup"><span data-stu-id="43954-114">Using Overload Groups</span></span>

<span data-ttu-id="43954-115">Überladungsgruppen bieten eine Methode zum Angeben der Argumentkombinationen, die in einer Aktivität gültig sind.</span><span class="sxs-lookup"><span data-stu-id="43954-115">Overload groups provide a method for indicating which combinations of arguments are valid in an activity.</span></span> <span data-ttu-id="43954-116">Argumente werden mit <xref:System.Activities.OverloadGroupAttribute> zusammen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="43954-116">Arguments are grouped together by using <xref:System.Activities.OverloadGroupAttribute>.</span></span> <span data-ttu-id="43954-117">Jeder Gruppe wird ein Name gegeben, der durch die <xref:System.Activities.OverloadGroupAttribute>angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="43954-117">Each group is given a name that is specified by the <xref:System.Activities.OverloadGroupAttribute>.</span></span> <span data-ttu-id="43954-118">Die Aktivität ist gültig, wenn nur ein Satz von Argumenten in einer Überladungsgruppe gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="43954-118">The activity is valid when only one set of arguments in an overload group are bound.</span></span> <span data-ttu-id="43954-119">Im folgenden Beispiel wird eine `CreateLocation`-Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="43954-119">In the following example, a `CreateLocation` class is defined.</span></span>  
  
```csharp  
class CreateLocation: Activity  
{  
    [RequiredArgument]  
    public InArgument<string> Name { get; set; }  
  
    public InArgument<string> Description { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G1")]  
    public InArgument<int> Latitude { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G1")]  
    public InArgument<int> Longitude { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    [OverloadGroup("G3")]  
    public InArgument<string> Street { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    public InArgument<string> City { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    public InArgument<string> State { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G3")]  
    public InArgument<int> Zip { get; set; }
}  
```  
  
 <span data-ttu-id="43954-120">Ziel dieser Aktivität ist es, einen Standort in den USA anzugeben.</span><span class="sxs-lookup"><span data-stu-id="43954-120">The objective of this activity is to specify a location in the US.</span></span> <span data-ttu-id="43954-121">Hierzu kann der Benutzer der Aktivität den Standort mithilfe von drei Argumentgruppen angeben.</span><span class="sxs-lookup"><span data-stu-id="43954-121">To do this, the user of the activity can specify the location using one of three groups of arguments.</span></span> <span data-ttu-id="43954-122">Zum Angeben gültiger Argumentkombinationen wurden drei Überladungsgruppen definiert.</span><span class="sxs-lookup"><span data-stu-id="43954-122">To specify the valid combinations of arguments, three overload groups are defined.</span></span> <span data-ttu-id="43954-123">`G1` enthält das `Latitude`-Argument und das `Longitude`-Argument.</span><span class="sxs-lookup"><span data-stu-id="43954-123">`G1` contains the `Latitude` and `Longitude` arguments.</span></span> <span data-ttu-id="43954-124">`G2` enthält `Street`, `City` und `State`.</span><span class="sxs-lookup"><span data-stu-id="43954-124">`G2` contains `Street`, `City`, and `State`.</span></span> <span data-ttu-id="43954-125">`G3` enthält `Street` und `Zip`.</span><span class="sxs-lookup"><span data-stu-id="43954-125">`G3` contains `Street` and `Zip`.</span></span> <span data-ttu-id="43954-126">`Name` ist ebenfalls ein erforderliches Argument, jedoch nicht Teil einer Überladungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="43954-126">`Name` is also a required argument, but it is not part of an overload group.</span></span> <span data-ttu-id="43954-127">Damit diese Aktivität gültig ist, müsste `Name` zusammen mit allen Argumenten aus einer (und nur einer) der Überladungsgruppen gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="43954-127">For this activity to be valid, `Name` would have to be bound together with all of the arguments from one and only one overload group.</span></span>  
  
 <span data-ttu-id="43954-128">Im folgenden Beispiel, das aus dem Beispiel [Datenbankzugriffsaktivitäten](./samples/database-access-activities.md) entnommen `ConnectionString` `ConfigFileSectionName`wurde, gibt es zwei Überladungsgruppen: und .</span><span class="sxs-lookup"><span data-stu-id="43954-128">In the following example, taken from the [Database Access Activities](./samples/database-access-activities.md) sample, there are two overload groups: `ConnectionString` and `ConfigFileSectionName`.</span></span> <span data-ttu-id="43954-129">Damit diese Aktivität gültig ist, müssen das `ProviderName`-Argument und das `ConnectionString`-Argument gebunden werden oder das `ConfigName`-Argument, jedoch nicht beides.</span><span class="sxs-lookup"><span data-stu-id="43954-129">For this activity to be valid, either the `ProviderName` and `ConnectionString` arguments must be bound, or the `ConfigName` argument, but not both.</span></span>  
  
```csharp  
public class DbUpdate: AsyncCodeActivity  
{  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
  
    [DependsOn("Parameters")]  
    public OutArgument<int> AffectedRecords { get; set; }
}  
```  
  
 <span data-ttu-id="43954-130">Beim Definieren einer Überladungsgruppe gilt:</span><span class="sxs-lookup"><span data-stu-id="43954-130">When defining an overload group:</span></span>  
  
- <span data-ttu-id="43954-131">Eine Überladungsgruppe darf keine Teilmenge bzw. kein äquivalenter Satz einer anderen Überladungsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="43954-131">An overload group cannot be a subset or an equivalent set of another overload group.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="43954-132">Es gibt allerdings eine Ausnahme zu dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="43954-132">There is one exception to this rule.</span></span> <span data-ttu-id="43954-133">Wenn eine Überladungsgruppe eine Teilmenge einer anderen Überladungsgruppe ist und die Teilmenge nur Argumente enthält, bei denen `RequiredArgument` gleich `false` ist, ist die Überladungsgruppe gültig.</span><span class="sxs-lookup"><span data-stu-id="43954-133">If an overload group is a subset of another overload group, and the subset contains only arguments where `RequiredArgument` is `false`, then the overload group is valid.</span></span>  
  
- <span data-ttu-id="43954-134">Überladungsgruppen können sich überschneiden. Dabei tritt jedoch ein Fehler auf, wenn die Schnittmenge der Gruppen alle erforderlichen Argumente einer oder beider Überladungsgruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="43954-134">Overload groups can overlap but it is an error if the intersection of the groups contains all the required arguments of one or both of the overload groups.</span></span> <span data-ttu-id="43954-135">Im vorherigen Beispiel trat eine Überschneidung zwischen der Überladungsgruppe `G2` und der Überladungsgruppe `G3` auf, aber da die Schnittmenge nicht alle Argumente einer oder beider Gruppen enthielt, war dies gültig.</span><span class="sxs-lookup"><span data-stu-id="43954-135">In the previous example the `G2` and `G3` overload groups overlapped, but because the intersection did not contain all the arguments of one or both of the groups this was valid.</span></span>  
  
 <span data-ttu-id="43954-136">Beim Binden von Argumenten in einer Überladungsgruppe gilt:</span><span class="sxs-lookup"><span data-stu-id="43954-136">When binding arguments in an overload group:</span></span>  
  
- <span data-ttu-id="43954-137">Eine Überladungsgruppe wird als gebunden angesehen, wenn alle `RequiredArgument`-Argumente in der Gruppe gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="43954-137">An overload group is considered bound if all the `RequiredArgument` arguments in the group are bound.</span></span>  
  
- <span data-ttu-id="43954-138">Wenn eine Gruppe über 0 `RequiredArgument`-Argumente verfügt und mindestens ein Argument gebunden ist, wird die Gruppe als gebunden betrachtet.</span><span class="sxs-lookup"><span data-stu-id="43954-138">If a group has zero `RequiredArgument` arguments and at least one argument bound, then the group is considered bound.</span></span>  
  
- <span data-ttu-id="43954-139">Es tritt ein Validierungsfehler auf, wenn keine der Überladungsgruppen gebunden ist, es sei denn, eine Überladungsgruppe enthält keine `RequiredArgument`-Argumente.</span><span class="sxs-lookup"><span data-stu-id="43954-139">It is a validation error if no overload groups are bound unless one overload group has no `RequiredArgument` arguments in it.</span></span>  
  
- <span data-ttu-id="43954-140">Es tritt ein Fehler auf, wenn mehr als eine Überladungsgruppe gebunden ist, d. h., wenn alle erforderlichen Argumente in einer Überladungsgruppe gebunden sind und zusätzlich ein weiteres Argument in einer anderen Überladungsgruppe gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="43954-140">It is an error to have more than one overload group bound, that is, all required arguments in one overload group are bound and any argument in another overload group is also bound.</span></span>
