---
title: SeedWork (wiederverwendbare Basisklassen und Schnittstellen für Ihr Domänenmodell)
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Verwenden des SeedWork-Konzepts als Ausgangspunkt zum Implementieren eines DDD-orientierten Domänenmodells
ms.date: 10/08/2018
ms.openlocfilehash: ab0aadc28dbd1175c75b04dadca29b7b0947f29b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116566"
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a>SeedWork (wiederverwendbare Basisklassen und Schnittstellen für Ihr Domänenmodell)

Der Projektmappenordner enthält den Ordner *SeedWork*. Dieser Ordner enthält benutzerdefinierte Basisklassen, die Sie als Grundlage Ihrer Domänenentitäten und Wertobjekte verwenden können. Mithilfe dieser Basisklassen vermeiden Sie redundanten Code in den Objektklassen der einzelnen Domänen. Der Ordner für diese Klassentypen heißt *SeedWork* und nicht *Framework* oder Ähnliches. Er heißt *SeedWork*, weil der Ordner nur eine kleine Teilmenge der wiederverwendbaren Klassen enthält, die eigentlich nicht als Framework betrachtet werden können. Der Begriff *SeedWork* wurde von [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) eingeführt und von [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) bekannt gemacht. Dieser Ordner kann jedoch auch z.B. „Common“ oder „SharedKernel“ heißen.

In Abbildung 7-12 werden die Klassen gezeigt, die im Microservice für Bestellungen den Stamm des Domänenmodells bilden. Er verfügt über einige benutzerdefinierte Basisklassen wie die „Entity“ (Entität), „Enumeration“ und ValueObject, sowie einige Schnittstellen. Diese Schnittstellen (IRepository und IUnitOfWork) informieren die Infrastrukturebene darüber, was implementiert werden muss. Diese Schnittstellen werden auch über die Abhängigkeitsinjektion von der Anwendungsebene verwendet.

:::image type="complex" source="./media/seedwork-domain-model-base-classes-interfaces/vs-solution-seedwork-classes.png" alt-text="Screenshot der Klassen, die im Ordner „SeedWork“ enthalten sind.":::
Der ausführliche Inhalt des Ordners „SeedWork“, der Basisklassen und -schnittstellen enthält: Entity.cs, Enumeration.cs, IAggregateRoot.cs, IRepository.cs, IUnitOfWork.cs und ValueObject.cs.
:::image-end:::

**Abbildung 7-12**. Beispiel für die „Seedwork“-Basisklassen und -Schnittstellen eines Domänenmodells

Viele Entwickler verwenden diese Vorgänge zum Kopieren und Einfügen (und kein formales Framework) projektübergreifend wieder. SeedWork-Ordner können in jeder Ebene oder Bibliothek vorkommen. Wenn die Anzahl der Klassen und Schnittstellen jedoch zu groß wird, sollten Sie eine einzelne Klassenbibliothek erstellen.

## <a name="the-custom-entity-base-class"></a>Die benutzerdefinierte Entity-Basisklasse

Der folgende Code ist ein Beispiel für eine Entity-Basisklasse, in der Sie Code platzieren können, der von jeder beliebigen Domänenentität genauso verwendet werden kann, z.B. Entitäts-ID, [Gleichheitsoperatoren](../../../csharp/language-reference/operators/equality-operators.md) oder eine Liste der Domänenereignisse pro Entität.

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
            // https://docs.microsoft.com/archive/blogs/ericlippert/guidelines-and-rules-for-gethashcode
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }
    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null));
        else
            return left.Equals(right);
    }
    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

Der vorherige Code mit einer Domänenereignisliste pro Entität wird in den nächsten Abschnitten erklärt werden, wenn es um Domänenereignisse geht.

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a>Repositoryverträge (Schnittstellen) auf der Ebene des Domänenmodells

Repositoryverträge sind einfache .NET-Schnittstellen, die die Vetragsanforderungen der Repositorys darstellen, die für jedes Aggregat verwendet werden sollen.

Die Repositorys selbst mit dem EF Core-Code oder anderen Infrastrukturabhängigkeiten und Code (LINQ, SQL etc.) dürfen nicht im Domänenmodell implementiert werden. Diese Repositorys sollten nur die im Domänenmodell definierten Schnittstellen implementieren.

Ein ähnliches Prinzip, bei dem die Repositoryschnittstellen in der Ebene des Domänenmodells platziert werden, ist das Schnittstellenaufteilungsprinzip. [Laut Martin Fowler](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) sollten Sie die Schnittstellenaufteilung nutzen, um eine Schnittstelle in einem Paket zu definieren und in einem anderen zu implementieren. So nimmt ein Client, der die Abhängigkeit von der Schnittstelle benötigt, keine Kenntnis von der Implementierung.

Wenn Sie das Schnittstellenaufteilungsprinzip verwenden, kann die Anwendungsebene (in diesem Fall das Web-API-Projekt für den Microservice) eine Abhängigkeit von den im Domänenmodell definierten Anforderungen aufweisen, jedoch keine direkte Abhängigkeit von der Infrastruktur-/Persistenzebene. Außerdem können Sie Abhängigkeitsinjektion verwenden, um die Implementierung zu isolieren, die in der Infrastruktur-/Persistenzebene mithilfe von Repositorys implementiert wurde.

Im folgenden Beispiel wird z.B. mithilfe der IOrderRepository-Schnittstelle definiert, welche Vorgänge die OrderRepository-Klasse auf der Infrastrukturebene implementieren muss. In der aktuellen Implementierung der Anwendung muss der Code nur der Datenbank Bestellungen hinzufügen oder diese aktualisieren, da Abfragen nach dem vereinfachten CQRS-Ansatz aufgeteilt werden.

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

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Martin Fowler. Separated Interface (Schnittstellenaufteilung)** \
  <https://www.martinfowler.com/eaaCatalog/separatedInterface.html>

>[!div class="step-by-step"]
>[Zurück](net-core-microservice-domain-model.md)
>[Weiter](implement-value-objects.md)
