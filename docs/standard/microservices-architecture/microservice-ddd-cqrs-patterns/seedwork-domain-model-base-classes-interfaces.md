---
title: SeedWork (wiederverwendbare Basisklassen und Schnittstellen für Ihr Domänenmodell)
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | SeedWork (wiederverwendbare Basisklassen und Schnittstellen für Ihr Domänenmodell)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.openlocfilehash: 7098bc1d37ecdf4826c0db6e754ca8df2ed72fe4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578052"
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="54559-103">SeedWork (wiederverwendbare Basisklassen und Schnittstellen für Ihr Domänenmodell)</span><span class="sxs-lookup"><span data-stu-id="54559-103">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="54559-104">Der Projektmappenordner enthält den Ordner *SeedWork*.</span><span class="sxs-lookup"><span data-stu-id="54559-104">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="54559-105">Der Ordner *SeedWork* enthält benutzerdefinierte Basisklassen, die Sie als Grundlage Ihrer Domänenentitäten und Wertobjekte verwenden können.</span><span class="sxs-lookup"><span data-stu-id="54559-105">The *SeedWork* folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="54559-106">Mithilfe dieser Basisklassen vermeiden Sie redundanten Code in den Objektklassen der einzelnen Domänen.</span><span class="sxs-lookup"><span data-stu-id="54559-106">Use these base classes so you do not have redundant code in each domain’s object class.</span></span> <span data-ttu-id="54559-107">Der Ordner für diese Klassentypen heißt *SeedWork* und nicht *Framework* oder Ähnliches.</span><span class="sxs-lookup"><span data-stu-id="54559-107">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="54559-108">Er heißt *SeedWork*, weil der Ordner nur eine kleine Teilmenge der wiederverwendbaren Klassen enthält, und diese stellen nicht wirklich ein Framework dar.</span><span class="sxs-lookup"><span data-stu-id="54559-108">It's called *SeedWork* because the folder contains just a small subset of reusable classes which cannot really be considered a framework.</span></span> <span data-ttu-id="54559-109">Der Begriff *SeedWork* wurde von [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) eingeführt und von [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) bekannt gemacht. Dieser Ordner kann jedoch auch z.B. „Common“ oder „SharedKernel“ heißen.</span><span class="sxs-lookup"><span data-stu-id="54559-109">*Seedwork* is a term introduced by [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="54559-110">In Abbildung 9-12 werden die Klassen gezeigt, die im Microservice für Bestellungen den Stamm des Domänenmodells bilden.</span><span class="sxs-lookup"><span data-stu-id="54559-110">Figure 9-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="54559-111">Er verfügt über einige benutzerdefinierte Basisklassen wie die „Entity“ (Entität), „Enumeration“ und ValueObject, sowie einige Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="54559-111">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="54559-112">Diese Schnittstellen (IRepository und IUnitOfWork) informieren die Infrastrukturebene darüber, was implementiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="54559-112">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="54559-113">Diese Schnittstellen werden auch über die Abhängigkeitsinjektion von der Anwendungsebene verwendet.</span><span class="sxs-lookup"><span data-stu-id="54559-113">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

![](./media/image13.PNG)

<span data-ttu-id="54559-114">**Abbildung 9-12:**</span><span class="sxs-lookup"><span data-stu-id="54559-114">**Figure 9-12**.</span></span> <span data-ttu-id="54559-115">Beispiel für die „Seedwork“-Basisklassen und -Schnittstellen eines Domänenmodells</span><span class="sxs-lookup"><span data-stu-id="54559-115">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="54559-116">Viele Entwickler verwenden diese Vorgänge zum Kopieren und Einfügen (und kein formales Framework) projektübergreifend wieder.</span><span class="sxs-lookup"><span data-stu-id="54559-116">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="54559-117">SeedWork-Ordner können in jeder Ebene oder Bibliothek vorkommen.</span><span class="sxs-lookup"><span data-stu-id="54559-117">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="54559-118">Wenn die Anzahl der Klassen und Schnittstellen jedoch zu groß wird, sollten Sie eine einzelne Klassenbibliothek erstellen.</span><span class="sxs-lookup"><span data-stu-id="54559-118">However, if the set of classes and interfaces gets big enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="54559-119">Die benutzerdefinierte Entity-Basisklasse</span><span class="sxs-lookup"><span data-stu-id="54559-119">The custom Entity base class</span></span>

<span data-ttu-id="54559-120">Der folgende Code ist ein Beispiel für eine Entity-Basisklasse, in der Sie Code platzieren können, der von jeder beliebigen Domänenentität genauso verwendet werden kann, z.B. Entitäts-ID, [Gleichheitsoperatoren](/cpp/cpp/equality-operators-equal-equal-and-exclpt-equal) oder eine Liste der Domänenereignisse pro Entität.</span><span class="sxs-lookup"><span data-stu-id="54559-120">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](/cpp/cpp/equality-operators-equal-equal-and-exclpt-equal), a domain event list per entity, etc.</span></span>

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE (1.1 and later)
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;    
    private List<INotification> _domainEvents;
    public virtual int Id 
    {
        get
        {
            return _Id;
        }
        protected set
        {
            _Id = value;
        }
    }

    public List<INotification> DomainEvents => _domainEvents;        
    public void AddDomainEvent(INotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<INotification>();
        _domainEvents.Add(eventItem);
    }
    public void RemoveDomainEvent(INotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }

    public bool IsTransient()
    {
        return this.Id == default(Int32);
    }

    public override bool Equals(object obj)
    {
        if (obj == null || !(obj is Entity))
            return false;
        if (Object.ReferenceEquals(this, obj))
            return true;
        if (this.GetType() != obj.GetType())
            return false;
        Entity item = (Entity)obj;
        if (item.IsTransient() || this.IsTransient())
            return false;
        else
            return item.Id == this.Id;
    }

    public override int GetHashCode()
    {
        if (!IsTransient())
        {
            if (!_requestedHashCode.HasValue)
                _requestedHashCode = this.Id.GetHashCode() ^ 31; 
            // XOR for random distribution. See:
            // http://blogs.msdn.com/b/ericlippert/archive/2011/02/28/guidelines-and-rules-for-gethashcode.aspx
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }
    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null)) ? true : false;
        else
            return left.Equals(right);
    }
    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

<span data-ttu-id="54559-121">Der vorherige Code mit einer Domänenereignisliste pro Entität wird in den nächsten Abschnitten erklärt werden, wenn es um Domänenereignisse geht.</span><span class="sxs-lookup"><span data-stu-id="54559-121">The previous code using a domain event list per entity will be explained in the next sections when focusing on domain events.</span></span> 

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="54559-122">Repositoryverträge (Schnittstellen) auf der Ebene des Domänenmodells</span><span class="sxs-lookup"><span data-stu-id="54559-122">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="54559-123">Repositoryverträge sind einfache .NET-Schnittstellen, die die Vetragsanforderungen der Repositorys darstellen, die für jedes Aggregat verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="54559-123">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span> 

<span data-ttu-id="54559-124">Die Repositorys selbst mit dem EF Core-Code oder anderen Infrastrukturabhängigkeiten und Code (LINQ, SQL etc.) dürfen nicht im Domänenmodell implementiert werden. Diese Repositorys sollten nur die von Ihnen definierte Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="54559-124">The repositories themselves, with EF Core code or any other infrastructure dependencies and code (Linq, SQL, etc.), must not be implemented within the domain model; the repositories should only implement the interfaces you define.</span></span> 

<span data-ttu-id="54559-125">Ein ähnliches Prinzip, bei dem die Repositoryschnittstellen in der Ebene des Domänenmodells platziert werden, ist das Schnittstellenaufteilungsprinzip.</span><span class="sxs-lookup"><span data-stu-id="54559-125">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="54559-126">[Laut Martin Fowler](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) sollten Sie die Schnittstellenaufteilung nutzen, um eine Schnittstelle in einem Paket zu definieren und in einem anderen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="54559-126">As [explained](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="54559-127">So nimmt ein Client, der die Abhängigkeit von der Schnittstelle benötigt, keine Kenntnis von der Implementierung.</span><span class="sxs-lookup"><span data-stu-id="54559-127">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="54559-128">Wenn Sie das Schnittstellenaufteilungsprinzip verwenden, kann die Anwendungsebene (in diesem Fall das Web-API-Projekt für den Microservice) eine Abhängigkeit von den im Domänenmodell definierten Anforderungen aufweisen, jedoch keine direkte Abhängigkeit von der Infrastruktur-/Persistenzebene.</span><span class="sxs-lookup"><span data-stu-id="54559-128">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="54559-129">Außerdem können Sie Abhängigkeitsinjektion verwenden, um die Implementierung zu isolieren, die in der Infrastruktur-/Persistenzebene mithilfe von Repositorys implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="54559-129">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="54559-130">Im folgenden Beispiel wird z.B. mithilfe der IOrderRepository-Schnittstelle definiert, welche Vorgänge die OrderRepository-Klasse auf der Infrastrukturebene implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="54559-130">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="54559-131">In der aktuellen Implementierung der Anwendung muss der Code nur der Datenbank Bestellungen hinzufügen oder diese aktualisieren, da Abfragen nach dem vereinfachten CQRS-Ansatz aufgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="54559-131">In the current implementation of the application, the code just needs to add or update orders to the database, since queries are split following the simplified CQRS approach.</span></span>

```csharp
// Defined at IOrderRepository.cs
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
        
    void Update(Order order);

    Task<Order> GetAsync(int orderId);
}

// Defined at IRepository.cs (Part of the Domain Seedwork)
public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a><span data-ttu-id="54559-132">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="54559-132">Additional resources</span></span>

-   <span data-ttu-id="54559-133">**Martin Fowler. Separated Interface (Schnittstellenaufteilung)**
    [*https://www.martinfowler.com/eaaCatalog/separatedInterface.html*](https://www.martinfowler.com/eaaCatalog/separatedInterface.html)</span><span class="sxs-lookup"><span data-stu-id="54559-133">**Martin Fowler. Separated Interface.**
[*https://www.martinfowler.com/eaaCatalog/separatedInterface.html*](https://www.martinfowler.com/eaaCatalog/separatedInterface.html)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="54559-134">[Zurück] (net-core-microservice-domain-model.md) [Weiter] (implement-value-objects.md)</span><span class="sxs-lookup"><span data-stu-id="54559-134">[Previous] (net-core-microservice-domain-model.md) [Next] (implement-value-objects.md)</span></span>
