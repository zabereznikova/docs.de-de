---
title: Implementieren die Microservice-Anwendungsebene mithilfe der Web-API
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren die Microservice-Anwendungsebene mithilfe der Web-API"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: d505a2561ae9b8dee05e803fd639387b63b28b70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-microservice-application-layer-using-the-web-api"></a>Implementieren die Microservice-Anwendungsebene mithilfe der Web-API

## <a name="using-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a>Mithilfe der Abhängigkeitsinjektion beim Einfügen von infrastrukturobjekte in Ihrer Anwendungsebene.

Wie bereits erwähnt, kann die Anwendungsschicht als Teil des Elements, das Sie erstellen, etwa innerhalb einer Web-API-Projekt oder ein MVC-Web-app-Projekt implementiert werden. Im Fall einer Microservice mit ASP.NET Core erstellt werden die Anwendungsebene in der Regel Ihre Web-API-Bibliothek. Gegebenenfalls trennen, was vom benutzerdefinierten Anwendungscode Ebene von ASP.NET Core (ihre Infrastruktur und Ihren Domänencontrollern) stammt, Ihrer Anwendungsebene konnte platziert werden, in einer separaten Klassenbibliothek, die ist jedoch optional.

Der Anwendungscode für die Ebene von der Reihenfolge Microservice wird z. B. direkt implementiert, als Teil der **Ordering.API** Projekt (einer ASP.NET Core Web-API), als gezeigt in Abbildung 9-19.

![](./media/image20.png)

**Abbildung 9 – 19**. Die Anwendungsebene im Projekt Ordering.API ASP.NET Core-Web-API

ASP.NET Core beinhaltet eine einfache [integrierte IoC-Container](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (dargestellt durch die IServiceProvider-Schnittstelle), konstruktoreinschleusung standardmäßig unterstützt und ASP.NET macht bestimmte Dienste DI erhältlich. ASP.NET Core wird mit dem Begriff *Service* für den Sie registrieren, Typen, die über DI-anforderungsumgebung eingefügt werden. Sie können den integrierten Container Dienste konfigurieren, in der ConfigureServices-Methode in Ihrer Anwendung Startklasse. Ihre Abhängigkeiten werden in den Diensten implementiert, die ein Typ benötigt.

In der Regel möchten Sie Abhängigkeiten einfügen, die infrastrukturobjekte implementieren. Eine sehr typische Abhängigkeit einfügen ist ein Repository. Aber Sie können eine Abhängigkeit für Infrastruktur, die Sie möglicherweise einfügen. Einfacher Implementierungen konnte Sie Ihr Unit of Work Muster-Objekt (das EF DbContext-Objekt) direkt einfügen, da ' DbContext ' auch die Implementierung Ihrer Infrastruktur Persistenz-Objekte ist.

Im folgenden Beispiel sehen Sie, wie die .NET Core durch den Konstruktor der erforderlichen Objekte Räumen ist. Die Klasse ist Befehlshandler, die im nächsten Abschnitt beschrieben wird.

```csharp
// Sample command handler
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;

    // Constructor where Dependencies are injected
    public CreateOrderCommandHandler(IOrderRepository orderRepository)
    {
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // ... Additional code
        //
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
            message.Country, message.ZipCode);
        var order = new Order(address, message.CardTypeId, message.CardNumber,
            message.CardSecurityNumber,
            message.CardHolderName,
            message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        //Persist the Order through the Repository
        _orderRepository.Add(order);
        var result = await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
        return result > 0;
    }
}
```

Die Klasse verwendet den eingefügten Repositorys durch Ausführen der Transaktion und wechselt der beizubehalten. Es spielt keine Rolle, ob diese Klasse Befehlshandler, eine ASP.NET Core Web-API-Controller-Methode ist oder eine [DDD Anwendungsdienst](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/). Letztlich ist es eine einfache Klasse, die ähnlich wie Befehlshandler-Repositorys, Domänenentitäten und anderen Anwendung Koordinierung verwendet. Abhängigkeit Injection funktioniert die gleiche Weise für die erwähnten Klassen, wie im Beispiel mithilfe der Abhängigkeitsinjektion auf den Konstruktor basieren.

### <a name="registering-the-dependency-implementation-types-and-interfaces-or-abstractions"></a>Registrierung der Abhängigkeitseigenschaft Implementierungstypen und Schnittstellen oder Abstraktionen

Bevor Sie die Objekte, die über Konstruktoren eingeschleust verwenden, müssen Sie wissen, wo Sie die Schnittstellen und Klassen, die die Objekte in Ihrer Anwendungsklassen über DI eingeschleust erzeugen zu registrieren. (Z. B. DI basierend auf den Konstruktor wie vorher gezeigt.)

#### <a name="using-the-built-in-ioc-container-provided-by-aspnet-core"></a>Mithilfe des integrierten IoC-Containers, die von ASP.NET Core bereitgestellt

Bei Verwendung den integrierten IoC-Container, die von ASP.NET Core bereitgestellten registrieren Sie die Typen, die Sie in der ConfigureServices-Methode in der Datei Startup.cs wie im folgenden Code einfügen möchten:

```csharp
// Registration of types into ASP.NET Core built-in container
public void ConfigureServices(IServiceCollection services)
{
    // Register out-of-the-box framework services.
    services.AddDbContext<CatalogContext>(c =>
    {
        c.UseSqlServer(Configuration["ConnectionString"]);
    },
    ServiceLifetime.Scoped
    );
    services.AddMvc();
    // Register custom application dependencies.
    services.AddScoped<IMyCustomRepository, MyCustomSQLRepository>();
}
```

Das bekannteste Muster beim Registrieren von Typen in einem IoC-Container besteht darin, ein Paar von Typen registrieren – eine Schnittstelle und die zugehörigen Implementierungsklasse. Wenn Sie ein Objekt aus dem IoC-Container mit einem beliebigen anderen Konstruktor anfordern, fordern Sie dann ein Objekt eines bestimmten Typs der Schnittstelle. Beispielsweise gibt im vorherigen Beispiel die letzte Zeile an, dass bei einer der Konstruktoren der IMyCustomRepository (Schnittstelle oder Abstraktion) eine Abhängigkeit aufweisen, IoC-Container eine Instanz der Implementierung MyCustomSQLServerRepository eingefügt werden. -Klasse.

#### <a name="using-the-scrutor-library-for-automatic-types-registration"></a>Mithilfe der Scrutor-Bibliothek für die Typen der automatischen Registrierung

Wenn DI in .NET Core verwenden, empfiehlt es sich in der Lage Überprüfung einer Assemblys und die Typen automatisch gemäß der Konvention zu registrieren. Dieses Feature ist zurzeit nicht verfügbar in ASP.NET Core. Sie können jedoch die [Scrutor](https://github.com/khellang/Scrutor) für diese Bibliothek. Dieser Ansatz eignet sich, wenn Sie Dutzende von Typen haben, die im IoC-Container registriert werden müssen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Matthew über allem. Registrieren von Diensten mit Scrutor**
    [*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)

<!-- -->

-   **Kristian Hellang. Scrutor.** GitHub-Repository.
    [*https://github.com/khellang/Scrutor*](https://github.com/khellang/Scrutor)

#### <a name="using-autofac-as-an-ioc-container"></a>Verwenden Autofac als IoC-container

Sie können auch zusätzliche IoC-Container verwenden, und schließen Sie diese in die Pipeline von ASP.NET Core, wie in der Reihenfolge Microservice in eShopOnContainers, der verwendet [Autofac](https://autofac.org/). Bei Verwendung von Autofac werden in der Regel die Typen über Module, die ermöglichen es Ihnen, teilen die Registrierung Typen zwischen mehreren Dateien je nach, die Typen befinden, ebenso wie Sie die Anwendungstypen, die über mehrere Klassenbibliotheken verteilt aufweisen können, registriert.

Folgendes ist z. B. die [Autofac Anwendungsmodul](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) für die [Ordering.API Web-API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) Projekt mit den Typen, die Sie einfügen möchten.

```csharp
public class ApplicationModule
    :Autofac.Module
{
    public string QueriesConnectionString { get; }
    public ApplicationModule(string qconstr)
    {
        QueriesConnectionString = qconstr;
    }

    protected override void Load(ContainerBuilder builder)
    {
        builder.Register(c => new OrderQueries(QueriesConnectionString))
            .As<IOrderQueries>()
            .InstancePerLifetimeScope();
        builder.RegisterType<BuyerRepository>()
            .As<IBuyerRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<OrderRepository>()
            .As<IOrderRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<RequestManager>()
            .As<IRequestManager>()
            .InstancePerLifetimeScope();
   }
}
```

Der Registrierungsvorgang und die Konzepte sind sehr ähnlich wie die Typen mit dem integrierten ASP.NET Core iOS-Container zu registrieren, aber die Syntax, die bei Verwendung von Autofac ist etwas anders.

Im Beispielcode wird die Abstraktion IOrderRepository zusammen mit der Implementierungsklasse OrderRepository registriert. Dies bedeutet, dass wenn ein Konstruktor eine Abhängigkeit über die IOrderRepository Abstraktion oder Schnittstelle deklariert, IoC-Container eine Instanz der Klasse OrderRepository einfügen.

Der Bereichstyp Instanz bestimmt, wie eine Instanz, die allen Anforderungen für den Dienst oder die Abhängigkeit gemeinsam genutzt wird. Wenn eine Anforderung für eine Abhängigkeit gestellt wird, kann der IoC-Container Folgendes zurück:

-   Eine einzelne Instanz pro Lebensdauer Bereich (gemäß dem ASP.NET Core IoC-Container als *im Bereich einer*).

-   Eine neue Instanz pro Abhängigkeit (gemäß dem ASP.NET Core IoC-Container als *vorübergehenden*).

-   Eine einzelne Instanz, die für alle Objekte, die mit der IoC-Container freigegeben (gemäß dem ASP.NET Core IoC-Container als *Singleton*).

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Einführung in die Abhängigkeitsinjektion in ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)

-   **Autofac.** Offizieller Dokumentation.
    [*http://docs.autofac.org/en/Latest/*](http://docs.autofac.org/en/latest/)

-   **Cesar de la Torre. Vergleichen von ASP.NET Core IoC-Container Dienst Lebensdauer mit Autofac IoC-Container Instanz Bereichen**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)

## <a name="implementing-the-command-and-command-handler-patterns"></a>Implementieren die Befehl und Befehlshandler Mustern

Im Beispiel DI-über-Konstruktor im vorherigen Abschnitt gezeigt wurde der IoC-Container Repositorys über einen Konstruktor in einer Klasse injiziert. Aber genau, wo wurden diese eingefügt? In einer einfachen Web-API (z. B. den Katalog Microservice in eShopOnContainers) fügen Sie sie auf der Ebene des MVC-Controller, in einem Controller-Konstruktor. Allerdings in den anfänglichen Code in diesem Abschnitt (die [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) Klasse aus dem Dienst Ordering.API in eShopOnContainers), die Einfügung des Abhängigkeiten erfolgt über den Konstruktor eines bestimmten Befehls Handler. Lassen Sie uns wird erläutert, welche Befehlshandler ist und warum Sie verwenden möchten.

Das Muster Befehl bezieht sich systemintern auf CQRS-Muster, die weiter oben in diesem Handbuch eingeführt wurde. CQRS verfügt über zwei Seiten. Der erste Bereich ist Abfragen unter Verwendung der vereinfachte Abfragen mit der [dapper, durch](https://github.com/StackExchange/dapper-dot-net) micro-ORM, die zuvor erläutert wurde. Der zweite Bereich ist die Befehle, die der Ausgangspunkt für Transaktionen und der Eingabekanal von außerhalb des Diensts sind.

Wie in Abbildung 9 – 20 dargestellt, das Muster basiert auf Befehle von der Clientseite akzeptieren basierend auf der die Domänenregeln für das Modell verarbeiten und schließlich die Status mit Transaktionen beibehalten.

![](./media/image21.png)

**Abbildung 9 – 20**. Überblick über die Befehle oder "transaktionale Seite" in einem CQRS-Muster

### <a name="the-command-class"></a>Die Befehlsklasse

Ein Befehl ist eine Anforderung für das System zum Ausführen einer Aktion, die den Zustand des Systems ändert. Befehle sind imperative und sollte nur einmal verarbeitet werden.

Da Befehle Erfordernisse sind, sie sind in der Regel mit einem Verb in die imperative Ton zu verwenden (z. B. "erstellen" oder "update") bezeichnet, und sie möglicherweise den aggregierten Typ, z. B. CreateOrderCommand enthalten. Im Gegensatz zu einer Veranstaltung ist ein Befehl nicht Fakten aus der Vergangenheit. Es ist nur eine Anforderung, und daher möglicherweise abgelehnt.

Befehle können über die Benutzeroberfläche als Ergebnis ein Benutzer eine Anforderung initiiert oder von einem Prozessmanager stammen, wenn der Prozess-Manager ein Aggregat zum Ausführen einer Aktion weitergeleitet wird.

Ein wichtiges Merkmal eines Befehls ist, dass es nur einmal von einem einzelnen Empfänger verarbeitet werden sollen. Dies ist ein Befehl ist eine einzelne Aktion oder die Transaktion, die Sie in der Anwendung durchführen möchten. Beispielsweise sollte der gleichen Reihenfolge Erstellungsbefehl nicht mehr als einmal verarbeitet werden. Dies ist ein wichtiger Unterschied zwischen Befehlen und Ereignissen. Ereignisse können mehrmals verarbeitet werden, da viele Systeme oder Microservices im Ereignis interessiert sein kann.

Darüber hinaus ist es wichtig, dass ein Befehl für den Fall, dass der Befehl nicht Idempotent ist nur ein Mal verarbeitet werden. Ein Befehl ist Idempotent, wenn sie mehrere Male ausgeführt werden kann ohne das Ergebnis, entweder aufgrund der Natur des Befehls oder aufgrund der Art und Weise, die des Systems den Befehl behandelt, zu ändern.

Es wird empfohlen, stellen Ihre Befehle und Idempotent aktualisiert, wenn es sinnvoll ist unter Ihrer Domäne Geschäftsregeln und Invarianten. Für die Instanz, um dasselbe Beispiel verwenden, wenn aus irgendeinem Grund (Wiederholungslogik, Hacker, usw.) der gleiche CreateOrder Befehl Ihr System mehrmals erreicht, sollte Sie es identifiziert und stellen Sie sicher, dass Sie nicht mehrere Aufträge erstellen können. Zu diesem Zweck müssen Sie irgendeine der Identität in der Betriebskonsole anzufügen und zu ermitteln, ob der Befehl oder das Update bereits verarbeitet wurde.

Sie senden ein Befehls an einen einzelnen Empfänger; einen Befehl Veröffentlichen nicht. Veröffentlichung ist für die integrationsereignisse, die einen Fakt Status –, dass etwas aufgetreten, und möglicherweise für Ereignisempfänger interessant sein. Im Fall von Ereignissen weist der Verleger keine Aspekte, die über die Empfänger erhalten, das Ereignis oder wie sie es verwenden. Aber integrationsereignisse sind bereits in vorherigen Abschnitten eingeführte anders.

Ein Befehl ist mit einer Klasse implementiert, die Datenfelder oder Sammlungen mit allen Informationen, die benötigt werden, um die Ausführung dieses Befehls enthält. Ein Befehl ist eine besondere Art von Daten übertragen Objekt (DTO), die speziell zum Anfordern von Änderungen oder Transaktionen verwendet wird. Der Befehl selbst basiert auf genau die Informationen, die für die mit dem Befehl, und keine weitere Verarbeitung erforderlich ist.

Das folgende Beispiel zeigt die vereinfachte CreateOrderCommand-Klasse. Dies ist eine unveränderliche-Befehl, der in der Reihenfolge Microservice in eShopOnContainers verwendet wird.

```csharp
// DDD and CQRS patterns comment
// Note that it is recommended that yuo implement immutable commands
// In this case, immutability is achieved by having all the setters as private
// plus being able to update the data just once, when creating the object
// through the constructor.
// References on immutable commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://msdn.microsoft.com/en-us/library/bb383979.aspx
[DataContract]
public class CreateOrderCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    private readonly List<OrderItemDTO> _orderItems;

    [DataMember]
    public string City { get; private set; }

    [DataMember]
    public string Street { get; private set; }

    [DataMember]
    public string State { get; private set; }

    [DataMember]
    public string Country { get; private set; }

    [DataMember]
    public string ZipCode { get; private set; }

    [DataMember]
    public string CardNumber { get; private set; }

    [DataMember]
    public string CardHolderName { get; private set; }

    [DataMember]
    public DateTime CardExpiration { get; private set; }

    [DataMember]
    public string CardSecurityNumber { get; private set; }

    [DataMember]
    public int CardTypeId { get; private set; }

    [DataMember]
    public IEnumerable<OrderItemDTO> OrderItems => _orderItems;

    public CreateOrderCommand()
    {
        _orderItems = new List<OrderItemDTO>();
    }

    public CreateOrderCommand(List<OrderItemDTO> orderItems, string city,
        string street,
        string state, string country, string zipcode,
        string cardNumber, string cardHolderName, DateTime cardExpiration,
        string cardSecurityNumber, int cardTypeId) : this()
    {
        _orderItems = orderItems;
        City = city;
        Street = street;
        State = state;
        Country = country;
        ZipCode = zipcode;
        CardNumber = cardNumber;
        CardHolderName = cardHolderName;
        CardSecurityNumber = cardSecurityNumber;
        CardTypeId = cardTypeId;
        CardExpiration = cardExpiration;
    }

    public class OrderItemDTO
    {
        public int ProductId { get; set; }
        public string ProductName { get; set; }
        public decimal UnitPrice { get; set; }
        public decimal Discount { get; set; }
        public int Units { get; set; }
        public string PictureUrl { get; set; }
    }
}
```

Die Befehlsklasse enthält im Grunde die zum Ausführen einer Geschäftstransaktion mithilfe der domänenmodellobjekten benötigten Daten. Daher sind die Befehle einfach Datenstrukturen, die schreibgeschützten Daten und kein Verhalten enthalten. Name des Befehls gibt ihren Zweck an. In vielen Sprachen wie C#\#, Befehle werden als Klassen dargestellt, aber sie sind nicht in dem Sinne real objektorientierte "true" Klassen.

Als eine zusätzliche Eigenschaft sind die Befehle unveränderlich, da die erwartete Verwendung ist, dass sie direkt von der Domänenmodell verarbeitet werden. Sie müssen nicht während ihrer Lebensdauer projizierten ändern. In einem C\# Klasse Unveränderlichkeit kann erreicht werden, da keine Setter oder andere Methoden, die internen Status ändern müssen.

Z. B. die Befehlsklasse zum Erstellen einer Bestellung ist wahrscheinlich ähnlich im Hinblick auf Daten der Bestellung, die Sie erstellen möchten, aber Sie wahrscheinlich nicht benötigen, dass dieselben Attribute. Beispielsweise verfügt CreateOrderCommand keine Auftrags-ID, da der Auftrag noch nicht erstellt wurde.

Viele Befehlsklassen kann einfach und erfordert nur wenige Felder über ein Zustand, der geändert werden muss. Das wäre der Fall, wenn Sie nur den Status einer Bestellung aus "in Bearbeitung" zu ändern "bezahlt" oder "geliefert", mit dem Befehl etwa wie folgt:

```csharp
[DataContract]
public class UpdateOrderStatusCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    public string Status { get; private set; }

    [DataMember]
    public string OrderId { get; private set; }

    [DataMember]
    public string BuyerIdentityGuid { get; private set; }
}
```

Einige Entwickler ihre Anforderung Benutzeroberflächenobjekte stellen ihre DTOs Befehl trennen, aber, die geht nur darum, Voreinstellung. Es ist ein zeitraubender Trennung mit nicht viel Nutzwerts, und die Objekte sind nahezu identisch mit der gleichen Form. Beispielsweise sind in verschiedenen eShopOnContainers, die Befehle direkt von der Clientseite.

### <a name="the-command-handler-class"></a>Der Befehlshandler-Klasse

Sie sollten eine bestimmten Befehl Handlerklasse für jeden Befehl implementieren. Ist die Funktionsweise des Musters, und es ist, in dem Sie das Command-Objekt, das Domänenobjekte und Repository-infrastrukturobjekte verwenden. Der Befehlshandler ist tatsächlich das Kernstück der Anwendungsschicht im Hinblick auf CQRS und DDD. Allerdings sollte die Domänenlogik innerhalb der Domänenklassen enthalten – innerhalb der aggregierten Stämme (Stamm-Entitäten), untergeordneten Entitäten, oder [Domänendienste](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), aber nicht innerhalb der Befehlshandler also eine Klasse von der Anwendung Ebene.

Befehlshandler einen Befehl empfängt und erhält ein Ergebnis aus dem Aggregat, das verwendet wird. Das Ergebnis sollte der Befehl erfolgreich ausgeführt wurde, oder aber eine Ausnahme sein. Im Falle einer Ausnahme sollte der Systemstatus nicht geändert werden.

Der Befehlshandler fließen i. d. r. die folgenden Schritte aus:

-   Er empfängt das Command-Objekt, wie ein DTO (aus der [Vermittler](https://en.wikipedia.org/wiki/Mediator_pattern) oder ein anderes Infrastrukturobjekt).

-   Er überprüft, dass der Befehl (sofern nicht durch den Vermittler überprüft) gültig ist.

-   Die aggregierten Stamminstanz, die das Ziel des aktuellen Befehls wird instanziiert.

-   Er führt die Methode für die aggregierten Stamminstanz Abrufen der erforderlichen Daten aus den Befehl.

-   Den neuen Zustand des Aggregats in die zugehörige Datenbank weiterhin auftritt. Dieser letzte Vorgang ist die aktuelle Transaktion.

Normalerweise befasst sich Befehlshandler mit einer einzelnen gesamtverstärkung durch aggregieren Stamm (Stammentität) gesteuert. Wenn mehrere Aggregate von den Empfang eines einzelnen Befehls betroffen sein sollen, können Sie Domäne Ereignisse verwenden, Status oder Aktionen über mehrere Aggregate weitergegeben

Wichtig dabei ist, dass bei der Verarbeitung eines Befehls die Domänenlogik innerhalb der Domänenmodell (Aggregate) vollständig gekapselten und bereit für die Komponententests werden soll. Befehlshandler dient lediglich als eine Möglichkeit, das Domänenmodell aus der Datenbank erhalten und als letzten Schritt informieren Sie die Infrastrukturebene (Repositorys), damit die Änderungen beibehalten, wenn das Modell geändert wird. Der Vorteil dieses Ansatzes ist, dass Sie die Domänenlogik in eine isolierte, vollständig gekapselten, umfangreiche, verhaltensbasierten Domänenmodell Umgestalten können, ohne Ändern des Codes in der Anwendung oder Infrastruktur-Ebenen, die sind die Aufgaben, die Ebene (Befehlshandler, Web-API -Repositorys, usw.).

Wenn Befehlshandler komplex sein, mit viel Logik erhalten, kann die anderen Code sein. Überprüfen sie, und findet Domänenlogik gestalten Sie den Code, um dieses Domänenverhalten auf die Methoden der Domänenobjekte (die aggregierten Stamm und untergeordnete Entität) zu verschieben.

Der folgende Code zeigt als ein Beispiel einer Command-Handler-Klasse die gleiche CreateOrderCommandHandler-Klasse, die Sie gesehen haben, am Anfang dieses Kapitels. In diesem Fall haben wir die Handle-Methode und die Vorgänge mit der Domäne Modell Objekte/Aggregaten hervorgehoben.

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IBuyerRepository _buyerRepository;
    private readonly IOrderRepository _orderRepository;

    public CreateOrderCommandHandler(IBuyerRepository buyerRepository,
        IOrderRepository orderRepository)
    {
        if (buyerRepository == null)
        {
            throw new ArgumentNullException(nameof(buyerRepository));
        }
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }

        _buyerRepository = buyerRepository;
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // Additional code ...
        //
        // Create the Order aggregate root
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var order = new Order(buyer.Id, payment.Id,
            new Address(message.Street,
            message.City, message.State,
            message.Country, message.ZipCode));

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        // Persist the Order through the aggregate's repository
        _orderRepository.Add(order);
        return await _orderRepository.UnitOfWork.SaveChangesAsync();
    }
}
```

Hierbei handelt es sich um zusätzliche Befehlshandler auszuführenden Schritte:

-   Verwenden Sie den Befehl Daten, mit des aggregierten Stamms Methoden und Verhalten verwendet werden kann.

-   Lösen Sie intern innerhalb der Domänenobjekte Domäne Ereignisse aus, während die Transaktion wird ausgeführt, sondern transparent aus einem Befehl Handler der Sicht.

-   Lösen Sie Wenn das Aggregat Ergebnis des Vorgangs erfolgreich ist, und nachdem die Transaktion abgeschlossen ist aus, Integration Ereignisse Befehlshandler. (Dies können auch von Infrastrukturklassen wie Repositorys ausgelöst werden.)

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Mark Seemann. Die Grenzen sind nicht mit dem objektorientierten**
    [*http://blog.ploeh.dk/2011/05/31/AttheBoundaries, ApplicationsareNotObject-orientierten /*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)

-   **Befehle und Ereignisse**
    [*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)

-   **Wie funktioniert die Befehlshandler? ** 
     [ *http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)

-   **Jimmy Bogard. Muster für den Befehl Domäne – Handler**
    [*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)

-   **Jimmy Bogard. Muster für den Befehl Domäne – Überprüfung**
    [*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a>Der Befehl Prozesspipeline: Befehlshandler auslösen

Die nächste Frage ist, wie Befehlshandler aufgerufen wird. Sie können manuell aus jedem zugehörigen ASP.NET Core Controller aufrufen. Ansatz zu wäre allerdings gekoppelt und ist nicht ideal.

Die anderen zwei Hauptoptionen, die die empfohlenen Optionen sind, sind:

-   Über ein Element der in-Memory-Vermittler-Muster.

-   Mit einer asynchronen Nachrichtenwarteschlange zwischen Domänencontrollern und Ereignishandler.

### <a name="using-the-mediator-pattern-in-memory-in-the-command-pipeline"></a>Mithilfe der Vermittler-Musters (in-Memory) in der Befehlspipeline

Wie in Abbildung 9-21 dargestellt, verwenden Sie in einem CQRS Ansatz eine intelligente Vermittler, ähnlich einem in-Memory-Bus, also intelligent genug, um die Umleitung an den richtigen Befehlshandler basierend auf dem Typ des Befehls oder des DTO empfangen werden. Die einzelnen schwarzen Pfeile zwischen Komponenten stellen die Abhängigkeiten zwischen Objekten (in vielen Fällen eingefügten mit DI) mit der zugehörigen Interaktionen dar.

![](./media/image22.png)

**Abbildung 9 – 21**. Mithilfe der Vermittler Muster im Prozess in einem einzelnen CQRS microservice

Der Grund, der unter Verwendung des Musters Vermittler sinnvoll ist, dass in Enterprise-Anwendungen, die verarbeitungsanforderungen komplizierte abrufen können. Sie möchten eine geöffnete Anzahl von querschnittliche Anliegen wie Protokollierung, Überprüfungen, Überwachung und Sicherheit hinzufügen können. In diesen Fällen können Sie auf eine Pipeline Vermittler basieren (finden Sie unter [Vermittler Muster](https://en.wikipedia.org/wiki/Mediator_pattern)) systemverarbeitungsaufwand für diese zusätzliche Verhaltensweisen oder querschnittliche Bedenken.

Ein Vermittler ist ein Objekt, das "wie" dieses Prozesses kapselt: koordiniert die Ausführung basierend auf Status, wie Befehlshandler aufgerufen wird oder der Nutzlast, die Sie an den Handler bereitstellen. Mit einer Komponente Vermittler können Sie querschnittliche Bedenken in einer zentralen und transparente Weise anwenden, durch Anwenden von Decorator-Elementen (oder [pipeline Verhalten](https://github.com/jbogard/MediatR/wiki/Behaviors) seit Vermittler v3). (Weitere Informationen finden Sie unter der [Decorator-Muster](https://en.wikipedia.org/wiki/Decorator_pattern).)

Decorator-Elementen und Verhaltensweisen ähneln [Aspekt Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming)nur auf eine bestimmte Prozesspipeline verwaltet, die von der Komponente Vermittler angewendet. Aspekte im AOP, die querschnittliche Bedenken implementieren werden basierend auf angewendet *Aspekt Weavers* eingefügten zum Zeitpunkt der Kompilierung oder basierend auf Objekt Aufruf abfangen. Beide Ansätze für typische AOP werden manchmal auch als "wie Magic," funktionieren, da er nicht schwer ist zu verstehen, wie AOP seine Arbeit ausführt. Beim Umgang mit schwerwiegenden Problemen oder Fehlern kann AOP Debuggen schwierig sein. Andererseits, sind diese Decorators/Verhaltensweisen explizite und nur im Rahmen der Vermittler angewendeten Debuggen wesentlich besser vorhersagbar und einfach.

Z. B. in der eShopOnContainers Microservice Sortierung, wir die beiden Beispiel Decorators implementiert eine [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) Klasse und ein [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) Klasse. Die Decorator-Implementierung wird im nächsten Abschnitt erläutert. Beachten Sie, dass in einer zukünftigen Version eShopOnContainers zu migrieren [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) und ans [Verhalten](https://github.com/jbogard/MediatR/wiki/Behaviors) anstelle von Decorator-Elementen.

### <a name="using-message-queues-out-of-proc-in-the-commands-pipeline"></a>Mithilfe von Nachrichtenwarteschlangen (Out-of-Proc) in den Befehl pipeline

Eine andere ist die Verwendung von asynchroner Nachrichten basierend auf Brokern oder Meldungswarteschlangen, wie in Abbildung 9 – 22 dargestellt. Diese Option kann auch mit der Vermittler Komponente direkt vor dem Befehlshandler kombiniert werden.

![](./media/image23.png)

**Abbildung 9 – 22**. Mithilfe von Nachrichtenwarteschlangen (außerhalb des Prozesses und Kommunikation zwischen Prozessen) mit CQRS-Befehlen

Mit Nachrichtentext zustimmen, werden weitere Befehle können mithilfe von Warteschlangen des Befehls Pipeline erschweren, da benötigen Sie wahrscheinlich die Pipeline in zwei Prozesse unterteilt, die über externe Nachrichtenwarteschlange verbunden sind. Es sollte dennoch verwendet werden, wenn müssen Sie die Skalierbarkeit und Leistung basierend auf asynchrones messaging verbessert werden können. Beachten Sie, dass im Fall von Abbildung 9 – 22, der Controller nur sendet der befehlsmeldung in die Warteschlange zurückgegeben. Die Nachrichten in ihrem eigenen Tempo wird anschließend der Befehlshandler verarbeiten. D. h. ein großer Vorteil von Warteschlangen – die Nachrichtenwarteschlange kann zu fungieren als Puffer in Fällen, wenn hyper Skalierbarkeit erforderlich, z. B. durch Aktien oder allen anderen Szenarien, die mit einer großen Datenmenge eingehend ist.

Allerdings müssen aufgrund der asynchronen Natur von Nachrichtenwarteschlangen, herauszufinden, wie für die Kommunikation mit der Clientanwendung über den Erfolg oder Misserfolg des Prozesses für den Befehl. In der Regel sollten Sie nie "fire and forget"-Befehle verwenden. Jede Business-Anwendung muss wissen, ob ein Befehl erfolgreich verarbeitet, oder mindestens überprüft und akzeptiert wurde.

Daher die Komplexität wird an den Client nach dem Validieren einer Befehlsnachricht, die an eine asynchrone Warteschlange übermittelt wurde reagieren Ihres Systems im Vergleich zu einem in-Process-Befehl-Prozess, der Ergebnis des Vorgangs gibt zurück, nachdem die Transaktion ausführt. Verwendung von Warteschlangen, müssen Sie das Ergebnis des Befehls Prozesses über anderen vorgangsmeldungen Ergebnis zurückzugeben, die zusätzliche Komponenten und benutzerdefinierte Kommunikation in Ihrem System benötigen.

Darüber hinaus sind asynchrone Befehle unidirektionale Befehle, die in vielen Fällen jedoch nicht benötigt werden möglicherweise wie im folgenden interessante Austausches zwischen Burtsev Alexey und Greg Young in erläutert wird, ein [online Konversation](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):

\[Burtsev Alexey\] : viel Code suchen, wo Personen Async befehlsverarbeitung oder unidirektionale Befehl messaging ohne aus irgendeinem Grund dazu verwenden (sie sind nicht ausführen eines langen Vorgangs, sie externe asynchronem Code nicht ausgeführt werden, diese Anwendung nicht selbst durchgestrichen die Grenze Nachrichtenbus verwenden werden). Warum führen sie diese unnötige Komplexität? Und ich noch nicht tatsächlich ein Codebeispiel CQRS mit Befehlshandler bisher blockiert gefunden, obwohl in den meisten Fällen gut geeignet sind.

\[Greg Young\] \[... \] ein asynchrones Befehls ist nicht vorhanden; es ist tatsächlich ein anderes Ereignis. Wenn ich muss übernehmen, was mich senden und ein Ereignis wird ausgelöst, wenn ich stimme nicht zu, ist es nicht mehr Sie darüber informiert, dass ich etwas tun. Es ist Sie darüber informiert mich, etwas vorgenommen wurde. Dies scheint zunächst einen geringfügigen Unterschied, verfügt aber über viele Auswirkungen.

Asynchrone Befehle erhöhen die Komplexität eines Systems zu erheblich, da es keine einfache Möglichkeit ist, Fehler hinweisen. Daher sind asynchrone Befehle nicht außer empfohlen, wenn skalierungsanforderungen benötigt werden oder in besonderen Fällen bei der Kommunikation von den internen Microservices über messaging. In diesen Fällen müssen Sie ein eigenes reporting und Recovery System zum Fehler entwerfen.

In der ursprünglichen Version von eShopOnContainers entschieden wir synchrone Verarbeitung von HTTP-Anforderungen gestartet und anhand des Musters Vermittler driven verwenden. Die leicht ermöglicht den Erfolg oder Misserfolg des Prozesses, wie in der [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) Implementierung.

In jedem Fall sollte dies eine Entscheidung auf Basis Ihrer Anwendung oder des Microservice geschäftlichen Anforderungen.

## <a name="implementing-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a>Implementieren der Prozesspipeline Befehl mit einem Vermittler-Muster (MediatR)

Als eine beispielimplementierung dieses Handbuchs mit in-Process-Pipeline, basierend auf den Vermittler Muster, mit dem Befehl "Erfassung" Laufwerk und routing, im Arbeitsspeicher, an die richtige-Befehlshandler vorgeschlagen werden. Das Handbuch auch vorgeschlagen Decorator-Elemente anwenden oder [Verhalten](https://github.com/jbogard/MediatR/wiki/Behaviors) um querschnittliche Aspekte zu trennen.

Bei Implementierung in .NET Core sind mehrere Open-Source-Bibliotheken verfügbar sind, die Vermittler-Muster implementieren. Die Bibliothek, die in diesem Handbuch verwendeten ist die [MediatR](https://github.com/jbogard/MediatR) Open Source-Bibliothek (Jimmy Bogard erstellt), aber Sie können einen anderen Ansatz verwenden. MediatR ist eine kleine und einfache-Bibliothek, die Ihnen ermöglicht, die in-Memory-Nachrichten, z. B. einen Befehl zu verarbeiten, beim Anwenden der Decorators oder Verhalten.

Mithilfe des Musters Vermittler zeigt Ihnen, verbundener Einzelsysteme zu verringern und isolieren die Probleme beim Herstellen der Verbindung automatisch an den Handler, der diese Aufgabe führt die erforderlichen Aufgaben – in diesem Fall um Befehlshandler.

Ein weiterer guter Grund das Muster der Vermittler verwendet wurde beim Überprüfen von diesem Handbuch Jimmy Bogard behandelt:

Ich denke Objektzuständen Testen hier ist es möglicherweise – es stellt ein nützliches konsistent Fenster, in das Verhalten Ihres Systems. Anforderung, Antwort Out. Wir haben diesen Aspekt überzeugendes im Gebäude konsistent verhält Tests gefunden.

Zunächst lassen Sie uns sehen Sie an den controllercode, in denen würden Sie tatsächlich den Vermittler-Objekt verwenden. Wenn Sie jedoch stattdessen das Vermittler nicht verwenden, müssen Sie alle Abhängigkeiten für diesen Controller, z. B. ein Protokollierungsobjekt und andere einfügen. Daher würde der Konstruktor ziemlich kompliziert sein. Andererseits, wenn Sie jedoch stattdessen das Vermittler verwenden, der Konstruktor der Domänencontroller viel einfacher, mit wenigen Abhängigkeiten anstatt viele Abhängigkeiten ist möglich, die eine pro querschnittliche-Vorgang, wie im folgenden Beispiel wäre:

```csharp
public class OrdersController : Controller
{
    public OrdersController(IMediator mediator,
        IOrderQueries orderQueries)
    // ...
```

Sie können sehen, dass der Vermittler einen sauberen und lean Web-API-Controller-Konstruktor zur Verfügung. Darüber hinaus wird der Code zum Senden eines Befehls auf den Vermittler-Objekt innerhalb der Controllermethoden fast nur eine Zeile:

```csharp
[Route("new")]
[HttpPost]
public async Task<IActionResult> CreateOrder([FromBody]CreateOrderCommand
    createOrderCommand)
{
    var commandResult = await _mediator.SendAsync(createOrderCommand);
    return commandResult ? (IActionResult)Ok() : (IActionResult)BadRequest();
}
```

In der Reihenfolge für MediatR zu Ihrem Ereignishandler Befehlsklassen berücksichtigen müssen Sie die Vermittler und der Befehl Handler-Klassen im IoC-Container zu registrieren. Standardmäßig MediatR Autofac als IoC-Container verwendet, aber Sie können auch die integrierte ASP.NET Core IoC-Container oder andere Container, die von MediatR unterstützt.

Der folgende Code zeigt, wie bei Autofac Module mithilfe der Vermittler Typen und Befehle zu registrieren.

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();
        builder.RegisterAssemblyTypes(typeof(CreateOrderCommand)
            .GetTypeInfo().Assembly)
            .As(o => o.GetInterfaces()
            .Where(i => i.IsClosedTypeOf(typeof(IAsyncRequestHandler<,>)))
            .Select(i => new KeyedService("IAsyncRequestHandler", i)));
        builder.RegisterGenericDecorator(typeof(LogDecorator<,>),
            typeof(IAsyncRequestHandler<,>), "IAsyncRequestHandler");

        // Other types registration
    }
}
```

Da jede Befehlshandler der Schnittstelle mit generischen IAsyncRequestHandler implementiert&lt;T&gt; und überprüft dann die RegisteredAssemblyTypes Objekt ist, wird der Handler ist in der Lage, jeden Befehl mit der Befehlshandler beziehen, da, Beziehung angegeben ist in der CommandHandler-Klasse, wie im folgenden Beispiel gezeigt:

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

Dies ist der Code, der Befehle mit Befehlshandler korreliert. Der Handler nur eine einfache Klasse vorhanden ist, aber es erbt von RequestHandler&lt;T&gt;, und MediatR wird sichergestellt, er ruft mit dem richtigen Nutzlast aufgerufen.

## <a name="applying-cross-cutting-concerns-when-processing-commands-with-the-mediator-and-decorator-patterns"></a>Anwenden von querschnittliche Aspekte bei der Verarbeitung von Befehlen mit den Vermittler und Decorator-Mustern

Es gibt noch etwas: querschnittliche Bedenken hinsichtlich der Vermittler Pipeline anwenden wird. Sie sehen auch am Ende der Autofac Registrierung Modulcode wie sie registriert wird, einen Decorator-Element eingeben, insbesondere eine benutzerdefinierte LogDecorator-Klasse.

Erneut, beachten Sie, dass eine zukünftige Version von eShopOnContainers ihn zum Migrieren [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) und ans [Verhalten](https://github.com/jbogard/MediatR/wiki/Behaviors) anstelle von Decorator-Elementen.

Dass [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) Klasse implementiert werden kann, wie der folgende Code, in dem Informationen zu ausgeführten Befehlshandler und gibt an, ob es erfolgreich war oder nicht protokolliert.

```csharp
public class LogDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly ILogger<LogDecorator<TRequest, TResponse>> _logger;

    public LogDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        ILogger<LogDecorator<TRequest, TResponse>> logger)
    {
        _inner = inner;
        _logger = logger;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        _logger.LogInformation($"Executing command {_inner.GetType().FullName}");
        var response = await _inner.Handle(message);
        _logger.LogInformation($"Succeeded executed command{_inner.GetType().FullName}");
        return response;
    }
}
```

Durch Implementieren dieser Decorator-Klasse und durch das ergänzen der Pipeline mit werden alle Befehle, die über MediatR verarbeitet Informationen zur Ausführung Protokollierung.

Die Sortierung Microservice gilt auch für einen zweiten Decorator-Element für grundlegende Validierungen eShopOnContainers der [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) Klasse, die benötigt die [FluentValidation](https://github.com/JeremySkinner/FluentValidation) Bibliothek, entsprechend der folgender Code:

```csharp
public class ValidatorDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly IValidator<TRequest>[] _validators;

    public ValidatorDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        IValidator<TRequest>[] validators)
    {
        _inner = inner;
        _validators = validators;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        var failures = _validators
            .Select(v => v.Validate(message))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();
            if (failures.Any())
            {
                throw new OrderingDomainException(
                $"Command Validation Errors for type {typeof(TRequest).Name}",
                new ValidationException("Validation exception", failures));
            }
            var response = await _inner.Handle(message);
        return response;
    }
}
```

Klicken Sie dann auf der Grundlage der [FluentValidation](https://github.com/JeremySkinner/FluentValidation) -Bibliothek erstellten Validierung für die Daten mit CreateOrderCommand, übergeben wird, wie im folgenden Code:

```csharp
public class CreateOrderCommandValidator : AbstractValidator<CreateOrderCommand>
{
    public CreateOrderCommandValidator()
    {
        RuleFor(command => command.City).NotEmpty();
        RuleFor(command => command.Street).NotEmpty();
        RuleFor(command => command.State).NotEmpty();
        RuleFor(command => command.Country).NotEmpty();
        RuleFor(command => command.ZipCode).NotEmpty();
        RuleFor(command => command.CardNumber).NotEmpty().Length(12, 19);
        RuleFor(command => command.CardHolderName).NotEmpty();
        RuleFor(command => command.CardExpiration).NotEmpty().Must(BeValidExpirationDate).
            WithMessage("Please specify a valid card expiration date");
        RuleFor(command => command.CardSecurityNumber).NotEmpty().Length(3);
        RuleFor(command => command.CardTypeId).NotEmpty();
        RuleFor(command => command.OrderItems).
            Must(ContainOrderItems).WithMessage("No order items found");
    }

    private bool BeValidExpirationDate(DateTime dateTime)
    {
        return dateTime >= DateTime.UtcNow;
    }

    private bool ContainOrderItems(IEnumerable<OrderItemDTO> orderItems)
    {
        return orderItems.Any();
    }
}
```

Sie können zusätzliche Überprüfungen erstellen. Dies ist eine sehr sauber und elegante Möglichkeit, Ihre Überprüfungen Befehl zu implementieren.

Auf ähnliche Weise könnten Sie andere Decorators für zusätzliche Aspekte oder querschnittliche Aspekte, die Sie auf Befehle angewendet, wenn sie behandeln möchten, implementieren.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

##### <a name="the-mediator-pattern"></a>Das Muster Vermittler

-   **Vermittler Muster**
    [*https://en.wikipedia.org/wiki/Mediator\_Muster*](https://en.wikipedia.org/wiki/Mediator_pattern)

##### <a name="the-decorator-pattern"></a>Das Decorator-Muster

-   **Decorator-Musters**
    [*https://en.wikipedia.org/wiki/Decorator\_Muster*](https://en.wikipedia.org/wiki/Decorator_pattern)

##### <a name="mediatr-jimmy-bogard"></a>MediatR (Jimmy Bogard)

-   **MediatR.** GitHub-Repository.
    [*https://github.com/jbogard/MediatR*](https://github.com/jbogard/MediatR)

-   **CQRS mit MediatR und AutoMapper**
    [*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)

-   **Fügen Sie Ihre Domänencontroller in einer Ernährung: POSTs und Befehle. ** 
     [ *https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)

-   **Bewältigt Fortschritts querschnittliche Aspekte, die eine Pipeline Vermittler**
    [*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)

-   **CQRS und REST: perfekte Übereinstimmung**
    [*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)

-   **Beispiele für die Pipeline MediatR**
    [*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)

-   **Vertikale Slice Testfixtures für MediatR und ASP.NET Core**
    *<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>*

-   **MediatR-Erweiterungen für Microsoft Abhängigkeitsinjektion freigegeben**
    [*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)

##### <a name="fluent-validation"></a>Fluent-Überprüfung

-   **Jeremy Skinner. FluentValidation.** GitHub-Repository.
    [*https://github.com/JeremySkinner/FluentValidation*](https://github.com/JeremySkinner/FluentValidation)

>[!div class="step-by-step"]
[Vorherigen] (Microservice-application-layer-web-api-design.md) [weiter] (.. /Implement-Resilient-Applications/Index.MD)
