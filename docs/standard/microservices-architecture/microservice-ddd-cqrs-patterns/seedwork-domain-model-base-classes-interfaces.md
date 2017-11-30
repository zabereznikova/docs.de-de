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
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a>Seedwork (wiederverwendbare Klassen und Schnittstellen für Ihre Domänenmodell)

Die Projektmappenordner enthält eine *SeedWork* Ordner. Die *SeedWork* Ordner enthält benutzerdefinierte Basisklassen, die Sie als Basis für Ihre Domänenentitäten und Wertobjekten verwenden können. Verwenden Sie diese Basisklassen, sodass Sie nicht redundanten Code in jeder Domäne-Objektklasse verfügen. Der Ordner für diese Typen Klassen wird aufgerufen, *SeedWork* und nicht etwas wie *Framework*. Es heißt *SeedWork* weil der Ordner nur eine kleine Teilmenge der wiederverwendbare Klassen enthält, das tatsächlich ein Framework angesehen werden kann. *Seedwork* ein Begriff eingeführt [Michael Feathers](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) und wurde durch den [Smell](https://martinfowler.com/bliki/Seedwork.html) aber nennen Sie diesen Ordner Allgemein, SharedKernel, auch oder ähnliches.

Abbildung 9 bis 12 zeigt die Klassen, die die Seedwork des Domänenmodells in der Reihenfolge Microservice bilden. Er verfügt über einige benutzerdefinierte Basisklassen wie die Entität, Enumerations- und ValueObject, sowie einige Schnittstellen. Diese Schnittstellen (IRepository und IUnitOfWork) informieren die Infrastrukturebene über herrscht implementiert werden. Diese Schnittstellen werden von der Anwendungsebene auch über die Abhängigkeitsinjektion verwendet.

![](./media/image13.PNG)

**Abbildung 9 bis 12**. Legen Sie ein Beispiel für Domäne Modell "Seedwork" Basis-Klassen und Schnittstellen

Dies ist der Typ der Wiederverwendung von kopieren und einfügen, die viele Entwickler mehrere Projekte, keine formale Framework gemeinsam zu verwenden. Sie können in jeder Ebene oder eine Bibliothek Seedworks haben. Wenn der Satz von Klassen und Schnittstellen groß genug ist, abruft, sollten Sie jedoch eine einzelne-Klassenbibliothek zu erstellen.

## <a name="the-custom-entity-base-class"></a>Die benutzerdefinierte Entität-Basisklasse

Der folgende Code ist ein Beispiel für eine Basisklasse für die Entität können Sie Code platzieren, die die gleiche Weise kann, durch eine beliebige Entität "Domain", z. B. die Entitäts-ID verwendet werden [Gleichheitsoperatoren](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx)usw..

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

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a>Repository Verträge (Schnittstellen) in der Domäne der Ebene

Repository-Verträge sind einfach .NET-Schnittstellen, die express die Vetragsanforderungen der Repositorys für jedes Aggregat verwendet werden soll. Selbst Repositorys EF Kerncode oder andere Infrastruktur Abhängigkeiten und Code müssen innerhalb des Domänenmodells nicht implementiert werden; die Repositorys sollten nur die Schnittstellen implementieren, die Sie definieren.

Ein Muster, die im Zusammenhang mit dieser Übung (platzieren die Repository-Schnittstellen in der Domäne der Ebene) ist die Schnittstelle getrennt-Muster. Als [erläutert](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) Smell, "Verwendung getrennt Schnittstelle so definieren Sie eine Schnittstelle in einem Paket aber in einer anderen zu implementieren. Auf diese Weise kann ein Client, der die Abhängigkeit auf die Schnittstelle benötigt die Implementierung nicht bewusst sein."

Nach dem Muster getrennt-Schnittstelle aktiviert der Anwendungsschicht (in diesem Fall das Web-API-Projekt für die Microservice) haben eine Abhängigkeit für die Anforderungen im Domänenmodell definiert, aber keine direkte Abhängigkeit auf der Infrastruktur/Persistenz Ebene. Sie können darüber hinaus Abhängigkeitsinjektion verwenden, um die Implementierung zu isolieren, die in der Infrastruktur implementiert wird mithilfe von Persistenzebene Repositorys.

Im folgende Beispiel mit der IOrderRepository-Schnittstelle definiert z. B. welche Vorgänge die OrderRepository-Klasse auf der Infrastrukturebene implementieren muss. In der aktuellen Implementierung der Anwendung muss der Code nur die Reihenfolge in der Datenbank hinzugefügt werden, da Abfragen Split folgen, wie Sie die CQS Ansatz und auftragsänderungen nicht implementiert werden.

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

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Martin Fowler. Getrennte-Schnittstelle. ** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)


>[!div class="step-by-step"]
[Vorherigen] (Net-Core-Microservice-Domain-model.md) [weiter] (implementieren-Wert-objects.md)
