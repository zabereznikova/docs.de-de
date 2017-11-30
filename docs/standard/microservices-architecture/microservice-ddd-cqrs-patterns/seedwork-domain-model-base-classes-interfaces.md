---
title: "Seedwork (wiederverwendbare Klassen und Schnittstellen für Ihre Domänenmodell)"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Seedwork (wiederverwendbare Klassen und Schnittstellen für Ihre Domänenmodell)"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 17602d94ea167997389a77f0d2358326258a8219
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="28dfc-104">Seedwork (wiederverwendbare Klassen und Schnittstellen für Ihre Domänenmodell)</span><span class="sxs-lookup"><span data-stu-id="28dfc-104">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="28dfc-105">Die Projektmappenordner enthält eine *SeedWork* Ordner.</span><span class="sxs-lookup"><span data-stu-id="28dfc-105">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="28dfc-106">Die *SeedWork* Ordner enthält benutzerdefinierte Basisklassen, die Sie als Basis für Ihre Domänenentitäten und Wertobjekten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="28dfc-106">The *SeedWork* folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="28dfc-107">Verwenden Sie diese Basisklassen, sodass Sie nicht redundanten Code in jeder Domäne-Objektklasse verfügen.</span><span class="sxs-lookup"><span data-stu-id="28dfc-107">Use these base classes so you do not have redundant code in each domain’s object class.</span></span> <span data-ttu-id="28dfc-108">Der Ordner für diese Typen Klassen wird aufgerufen, *SeedWork* und nicht etwas wie *Framework*.</span><span class="sxs-lookup"><span data-stu-id="28dfc-108">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="28dfc-109">Es heißt *SeedWork* weil der Ordner nur eine kleine Teilmenge der wiederverwendbare Klassen enthält, das tatsächlich ein Framework angesehen werden kann.</span><span class="sxs-lookup"><span data-stu-id="28dfc-109">It's called *SeedWork* because the folder contains just a small subset of reusable classes which cannot really be considered a framework.</span></span> <span data-ttu-id="28dfc-110">*Seedwork* ein Begriff eingeführt [Michael Feathers](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) und wurde durch den [Smell](https://martinfowler.com/bliki/Seedwork.html) aber nennen Sie diesen Ordner Allgemein, SharedKernel, auch oder ähnliches.</span><span class="sxs-lookup"><span data-stu-id="28dfc-110">*Seedwork* is a term introduced by [Michael Feathers](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="28dfc-111">Abbildung 9 bis 12 zeigt die Klassen, die die Seedwork des Domänenmodells in der Reihenfolge Microservice bilden.</span><span class="sxs-lookup"><span data-stu-id="28dfc-111">Figure 9-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="28dfc-112">Er verfügt über einige benutzerdefinierte Basisklassen wie die Entität, Enumerations- und ValueObject, sowie einige Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="28dfc-112">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="28dfc-113">Diese Schnittstellen (IRepository und IUnitOfWork) informieren die Infrastrukturebene über herrscht implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="28dfc-113">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="28dfc-114">Diese Schnittstellen werden von der Anwendungsebene auch über die Abhängigkeitsinjektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="28dfc-114">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

![](./media/image13.PNG)

<span data-ttu-id="28dfc-115">**Abbildung 9 bis 12**.</span><span class="sxs-lookup"><span data-stu-id="28dfc-115">**Figure 9-12**.</span></span> <span data-ttu-id="28dfc-116">Legen Sie ein Beispiel für Domäne Modell "Seedwork" Basis-Klassen und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="28dfc-116">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="28dfc-117">Dies ist der Typ der Wiederverwendung von kopieren und einfügen, die viele Entwickler mehrere Projekte, keine formale Framework gemeinsam zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="28dfc-117">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="28dfc-118">Sie können in jeder Ebene oder eine Bibliothek Seedworks haben.</span><span class="sxs-lookup"><span data-stu-id="28dfc-118">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="28dfc-119">Wenn der Satz von Klassen und Schnittstellen groß genug ist, abruft, sollten Sie jedoch eine einzelne-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="28dfc-119">However, if the set of classes and interfaces gets big enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="28dfc-120">Die benutzerdefinierte Entität-Basisklasse</span><span class="sxs-lookup"><span data-stu-id="28dfc-120">The custom Entity base class</span></span>

<span data-ttu-id="28dfc-121">Der folgende Code ist ein Beispiel für eine Basisklasse für die Entität können Sie Code platzieren, die die gleiche Weise kann, durch eine beliebige Entität "Domain", z. B. die Entitäts-ID verwendet werden [Gleichheitsoperatoren](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx)usw..</span><span class="sxs-lookup"><span data-stu-id="28dfc-121">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx), etc.</span></span>

```csharp
// ENTITY FRAMEWORK CORE 1.1
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;

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
                _requestedHashCode = this.Id.GetHashCode() \^ 31;
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

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="28dfc-122">Repository Verträge (Schnittstellen) in der Domäne der Ebene</span><span class="sxs-lookup"><span data-stu-id="28dfc-122">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="28dfc-123">Repository-Verträge sind einfach .NET-Schnittstellen, die express die Vetragsanforderungen der Repositorys für jedes Aggregat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="28dfc-123">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span> <span data-ttu-id="28dfc-124">Selbst Repositorys EF Kerncode oder andere Infrastruktur Abhängigkeiten und Code müssen innerhalb des Domänenmodells nicht implementiert werden; die Repositorys sollten nur die Schnittstellen implementieren, die Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="28dfc-124">The repositories themselves, with EF Core code or any other infrastructure dependencies and code, must not be implemented within the domain model; the repositories should only implement the interfaces you define.</span></span>

<span data-ttu-id="28dfc-125">Ein Muster, die im Zusammenhang mit dieser Übung (platzieren die Repository-Schnittstellen in der Domäne der Ebene) ist die Schnittstelle getrennt-Muster.</span><span class="sxs-lookup"><span data-stu-id="28dfc-125">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="28dfc-126">Als [erläutert](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) Smell, "Verwendung getrennt Schnittstelle so definieren Sie eine Schnittstelle in einem Paket aber in einer anderen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="28dfc-126">As [explained](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="28dfc-127">Auf diese Weise kann ein Client, der die Abhängigkeit auf die Schnittstelle benötigt die Implementierung nicht bewusst sein."</span><span class="sxs-lookup"><span data-stu-id="28dfc-127">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="28dfc-128">Nach dem Muster getrennt-Schnittstelle aktiviert der Anwendungsschicht (in diesem Fall das Web-API-Projekt für die Microservice) haben eine Abhängigkeit für die Anforderungen im Domänenmodell definiert, aber keine direkte Abhängigkeit auf der Infrastruktur/Persistenz Ebene.</span><span class="sxs-lookup"><span data-stu-id="28dfc-128">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="28dfc-129">Sie können darüber hinaus Abhängigkeitsinjektion verwenden, um die Implementierung zu isolieren, die in der Infrastruktur implementiert wird mithilfe von Persistenzebene Repositorys.</span><span class="sxs-lookup"><span data-stu-id="28dfc-129">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="28dfc-130">Im folgende Beispiel mit der IOrderRepository-Schnittstelle definiert z. B. welche Vorgänge die OrderRepository-Klasse auf der Infrastrukturebene implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="28dfc-130">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="28dfc-131">In der aktuellen Implementierung der Anwendung muss der Code nur die Reihenfolge in der Datenbank hinzugefügt werden, da Abfragen Split folgen, wie Sie die CQS Ansatz und auftragsänderungen nicht implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="28dfc-131">In the current implementation of the application, the code just needs to add the order to the database, since queries are split following the CQS approach, and updates to orders are not implemented.</span></span>

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
}

public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a><span data-ttu-id="28dfc-132">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="28dfc-132">Additional resources</span></span>

-   <span data-ttu-id="28dfc-133">**Martin Fowler. Getrennte-Schnittstelle. ** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span><span class="sxs-lookup"><span data-stu-id="28dfc-133">**Martin Fowler. Separated Interface.**
[*http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="28dfc-134">[Vorherigen] (Net-Core-Microservice-Domain-model.md) [weiter] (implementieren-Wert-objects.md)</span><span class="sxs-lookup"><span data-stu-id="28dfc-134">[Previous] (net-core-microservice-domain-model.md) [Next] (implement-value-objects.md)</span></span>
