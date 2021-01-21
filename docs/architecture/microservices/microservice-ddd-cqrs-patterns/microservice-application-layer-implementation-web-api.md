---
title: Implementieren der Microservice-Anwendungsschicht mithilfe der Web-API
description: Übersicht über die Abhängigkeitsinjektion und Vermittlermuster und ihre Implementierung in der Web-API Anwendungsschicht.
ms.date: 01/13/2021
ms.openlocfilehash: bf37b0bfc7d9438752673d1c617657822b2a48ad
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188971"
---
# <a name="implement-the-microservice-application-layer-using-the-web-api"></a>Implementieren der Microserviceanwendungsschicht mithilfe der Web-API

## <a name="use-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a>Einfügen von Infrastrukturobjekten in die Anwendungsschicht mithilfe der Abhängigkeitsinjektion

Wie bereits erwähnt, kann die Anwendungsschicht als Teil des Artefakts (der Assembly) implementiert werden, das Sie erstellen, etwa innerhalb eines Web-API-Projekts oder eines MVC-Web-App-Projekts. Im Falle eines mit ASP.NET Core erstellten Microservice ist die Anwendungsschicht in der Regel Ihre Web-API-Bibliothek. Wenn Sie das, was von ASP.NET Core stammt (dessen Infrastruktur und Ihren Domänencontroller) von Ihrem benutzerdefinierten Anwendungsschichtcode trennen möchten, können Sie Ihre Anwendungsschicht auch in einer separaten Klassenbibliothek platzieren. Dies ist jedoch optional.

Der Anwendungsschichtcode des Microservices für Bestellungen ist beispielsweise direkt als Teil des **Ordering.API**-Projekts (ein ASP.NET Core-Web-API-Projekt) implementiert (s. Abbildung 7-23).

:::image type="complex" source="./media/microservice-application-layer-implementation-web-api/ordering-api-microservice.png" alt-text="Screenshot des Microservice „Ordering.API“ im Projektmappen-Explorer.":::
Der Projektmappen-Explorer des Microservice „Ordering.API“, der die Unterordner von „Anwendung“ anzeigt: Verhalten, Befehle, DomainEventHandlers, IntegrationEvents, Modelle, Abfragen und Prüfungen.
:::image-end:::

**Abbildung 7-23**. Die Anwendungsschicht im Projekt Ordering.API-Projekt (ASP.NET Core-Web-API-Projekt)

ASP.NET Core enthält einen einfachen [integrierten Container](/aspnet/core/fundamentals/dependency-injection) (dargestellt durch die IServiceProvider-Schnittstelle), der die Constructor Injection standardmäßig unterstützt. Zudem stellt ASP.NET bestimmte Dienste über Dependency Injection zur Verfügung. ASP.NET Core verwendet den Begriff *Dienst* für alle Typen, die Sie registrieren und die über DI eingefügt werden. Sie konfigurieren die integrierten Containerdienste in der ConfigureServices-Methode in der Startup-Klasse Ihrer Anwendung. Ihre Abhängigkeiten werden in den Diensten implementiert, die ein Typ benötigt und die Sie im IoC-Container registrieren.

In der Regel fügen Sie Abhängigkeiten ein, die Infrastrukturobjekte implementieren. Eine typische einzufügende Abhängigkeit ist ein Repository. Sie können jedoch auch jede andere Infrastrukturabhängigkeit einfügen, die verfügbar ist. Für einfachere Implementierungen können Sie Ihr Arbeitseinheitsmuster-Objekt (EF DbContext-Objekt) direkt einfügen, da der DBContext auch die Implementierung Ihrer Infrastrukturpersistenzobjekte ist.

Im folgenden Beispiel sehen Sie, wie .NET die erforderlichen Repositoryobjekte über den Konstruktor einfügt. Die Klasse ist ein Befehlshandler und wird im nächsten Abschnitt beschrieben.

```csharp
public class CreateOrderCommandHandler
        : IRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;
    private readonly IOrderingIntegrationEventService _orderingIntegrationEventService;
    private readonly ILogger<CreateOrderCommandHandler> _logger;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
        IOrderingIntegrationEventService orderingIntegrationEventService,
        IOrderRepository orderRepository,
        IIdentityService identityService,
        ILogger<CreateOrderCommandHandler> logger)
    {
        _orderRepository = orderRepository ?? throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ?? throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ?? throw new ArgumentNullException(nameof(mediator));
        _orderingIntegrationEventService = orderingIntegrationEventService ?? throw new ArgumentNullException(nameof(orderingIntegrationEventService));
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
    }

    public async Task<bool> Handle(CreateOrderCommand message, CancellationToken cancellationToken)
    {
        // Add Integration event to clean the basket
        var orderStartedIntegrationEvent = new OrderStartedIntegrationEvent(message.UserId);
        await _orderingIntegrationEventService.AddAndSaveEventAsync(orderStartedIntegrationEvent);

        // Add/Update the Buyer AggregateRoot
        // DDD patterns comment: Add child entities and value-objects through the Order Aggregate-Root
        // methods and constructor so validations, invariants and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State, message.Country, message.ZipCode);
        var order = new Order(message.UserId, message.UserName, address, message.CardTypeId, message.CardNumber, message.CardSecurityNumber, message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice, item.Discount, item.PictureUrl, item.Units);
        }

        _logger.LogInformation("----- Creating Order - Order: {@Order}", order);

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync(cancellationToken);
    }
}

```

Die Klasse verwendet die eingefügten Repositorys zum Ausführen der Transaktion und Beibehalten der Zustandsänderungen. Es spielt keine Rolle, ob diese Klasse ein Befehlshandler, eine Web-API-Controller-Methode von ASP.NET Core oder ein [DDD-Anwendungsdienst](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/) ist. Letztlich handelt es sich um eine einfache Klasse, die Repositorys, Domänenentitäten und die sonstige Anwendungskoordinierung auf eine mit einem Befehlshandler vergleichbare Art und Weise verwendet. Die Dependency Injection funktioniert auf die gleiche Weise für alle erwähnten Klassen, wie etwa im Beispiel, in dem die DI basierend auf dem Konstruktor verwendet wird.

### <a name="register-the-dependency-implementation-types-and-interfaces-or-abstractions"></a>Registrieren von Abhängigkeitsimplementierungstypen und Schnittstellen oder Abstraktionen

Bevor Sie die Objekte verwenden, die über Konstruktoren eingefügt werden, müssen Sie wissen, wo Sie die Schnittstellen und Klassen registrieren, die die über die DI in Ihre Anwendungsklassen eingefügten Objekte erstellen. (Wie DI basierend auf den Konstruktor, wie weiter oben dargestellt.)

#### <a name="use-the-built-in-ioc-container-provided-by-aspnet-core"></a>Verwenden des integrierten und von ASP.NET Core bereitgestellten IoC-Containers

Bei Verwendung des integrierten IoC-Containers, der von ASP.NET Core bereitgestellt wird, registrieren Sie die Typen, die Sie in die ConfigureServices-Methode in der Datei Startup.cs wie im folgenden Code einfügen möchten:

```csharp
// Registration of types into ASP.NET Core built-in container
public void ConfigureServices(IServiceCollection services)
{
    // Register out-of-the-box framework services.
    services.AddDbContext<CatalogContext>(c =>
        c.UseSqlServer(Configuration["ConnectionString"]),
        ServiceLifetime.Scoped);

    services.AddMvc();
    // Register custom application dependencies.
    services.AddScoped<IMyCustomRepository, MyCustomSQLRepository>();
}
```

Das bekannteste Muster beim Registrieren von Typen in einem IoC-Container ist die Registrierung eines Typenpaars, d.h. eine Schnittstelle und die zugehörige Implementierungsklasse. Wenn Sie ein Objekt aus dem IoC-Container über einen beliebigen anderen Konstruktor anfordern, fordern Sie ein Objekt eines bestimmten Schnittstellentyps an. Beispielsweise gibt die letzte Zeile aus dem vorherigen Beispiel an, dass der IoC-Container eine Instanz der MyCustomSQLServerRepository-Implementierungsklasse einfügt, wenn Ihre Konstruktoren eine Abhängigkeit von IMyCustomRepository (Schnittstellen oder Abstraktion) aufweisen.

#### <a name="use-the-scrutor-library-for-automatic-types-registration"></a>Verwenden der Scrutor-Bibliothek zur automatischen Typenregistrierung

Bei Verwendung der DI in .NET empfiehlt es sich, eine Assembly zu überprüfen und ihre Typen automatisch gemäß Konvention zu registrieren. Dieses Feature ist in ASP.NET Core derzeit nicht verfügbar. Sie können jedoch die [Scrutor](https://github.com/khellang/Scrutor)-Bibliothek zu diesem Zweck verwenden. Dieser Ansatz eignet sich, wenn Sie Dutzende von Typen haben, die im IoC-Container registriert werden müssen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Matthew King. Registering services with Scrutor (Registrieren von Diensten mit Scrutor)**  \
  <https://www.mking.net/blog/registering-services-with-scrutor>

- **Kristian Hellang. Scrutor.** GitHub-Repository. \
  <https://github.com/khellang/Scrutor>

#### <a name="use-autofac-as-an-ioc-container"></a>Verwenden von Autofac als IoC-Container

Sie können auch zusätzliche IoC-Container verwenden und diese direkt an die Pipeline von ASP.NET Core anschließen, wie z.B. im Microservice für Bestellung in eShopOnContainers, der [Autofac](https://autofac.org/) verwendet. Bei Verwendung von Autofac werden in der Regel die Typen über Module registriert, die ermöglichen, die Registrierungstypen zwischen mehreren Dateien je nachdem zu teilen, wo sich die Typen befinden. Die Anwendungstypen können aber auch über mehrere Klassenbibliotheken verteilt sein.

Das folgende Modul beispielsweise ist das [Autofac-Anwendungsmodul](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) für das [Ordering.API-Web-API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API)-Projekt mit den Typen, die Sie einfügen möchten.

```csharp
public class ApplicationModule : Autofac.Module
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

Autofac hat auch eine Funktion, um [Assemblys und Registertypen auf Namenskonventionen](https://autofac.readthedocs.io/en/latest/register/scanning.html) zu überprüfen.

Der Registrierungsvorgang und die Konzepte ähneln stark der Methode für die Typenregistrierung mit dem integrierten ASP.NET Core-IoC-Container, aber die Syntax unterscheidet sich geringfügig bei der Verwendung von Autofac.

Im Beispielcode wird die Abstraktion IOrderRepository zusammen mit der Implementierungsklasse OrderRepository registriert. Dies bedeutet, dass IoC-Container eine Instanz der OrderRepository-Klasse einfügen, wenn ein Konstruktor eine Abhängigkeit über die IOrderRepository-Abstraktion oder -Schnittstelle deklariert.

Der Instanzbereichstyp bestimmt, wie eine Instanz von Anforderungen für den gleichen Dienst oder die gleiche Abhängigkeit gemeinsam genutzt wird. Wenn eine Anforderung für eine Abhängigkeit gestellt wird, kann der IoC-Container Folgendes zurückgeben:

- Eine einzelne Instanz pro Lebensdauerbereich (gemäß dem ASP.NET Core-IoC-Container *bereichsbezogen*).

- Eine neue Instanz pro Abhängigkeit (gemäß dem ASP.NET Core-IoC-Container *vorübergehend*).

- Eine einzelne Instanz, die von allen Objekten gemeinsam genutzt wird, die den IoC-Container verwenden (gemäß dem ASP.NET Core IoC-Container *Singleton*).

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Einführung in Abhängigkeitsinjektion in ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection](/aspnet/core/fundamentals/dependency-injection)

- **Autofac.** Offizielle Dokumentation. \
  <https://docs.autofac.org/en/latest/>

- **Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes – Cesar de la Torre (Vergleichen der Lebensdauer von Containerdiensten mit ASP.NET Core IoC und Autofac IoC-Containerinstanzbereichen – Cesar de la Torre** \
  <https://devblogs.microsoft.com/cesardelatorre/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/>

## <a name="implement-the-command-and-command-handler-patterns"></a>Implementieren von Befehls- und Befehlshandlermustern

Im Beispiel DI-über-Konstruktor im vorherigen Abschnitt hat der IoC-Container Repositorys über einen Konstruktor in einer Klasse eingefügt. Aber wo genau wurden diese eingefügt? In einer einfachen Web-API (z. B. im Katalogmicroservice in eShopOnContainers) fügen Sie sie auf der Ebene des MVC-Controllers als Teil der Anforderungspipeline von ASP.NET Core in einen Controllerkonstruktor ein. Allerdings erfolgt die Einfügung von Abhängigkeiten im anfänglichen Code in diesem Abschnitt ([CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs)-Klasse aus dem Ordering.API-Dienst in eShopOnContainers) über den Konstruktor eines bestimmten Befehlshandlers. Lassen Sie uns erklären, was ein Befehlshandler ist und weshalb Sie ihn verwenden sollten.

Das Befehlsmuster bezieht sich systemintern auf das CQRS-Muster, das weiter oben in dieser Anleitung erläutert wurde. CQRS verfügt über zwei Seiten. Der erste Bereich sind Abfragen unter Verwendung vereinfachter Abfragen mit der [Dapper](https://github.com/StackExchange/dapper-dot-net)-micro-ORM, der zuvor erläutert wurde. Der zweite Bereich sind Befehle, die der Ausgangspunkt für Transaktionen sind, und der Eingabekanal außerhalb des Diensts.

Wie in Abbildung 7-24 dargestellt, basiert das Muster auf der clientseitigen Annahme von Befehlen, ihre Verarbeitung auf Grundlage von Domänenmodellregeln und schließlich auf der Beibehaltung der Status mit Transaktionen.

![Diagramm: allgemeiner Datenfluss vom Client zur Datenbank](./media/microservice-application-layer-implementation-web-api/high-level-writes-side.png)

**Abbildung 7-24**. Überblick über die Befehle oder die „Transaktionsseite“ in einem CQRS-Muster

Abbildung 7–24 zeigt, dass die Benutzeroberflächen-App einen Befehl über die API sendet, der zu einem `CommandHandler` gelangt, der vom Domänenmodell und der Infrastruktur abhängt, um die Datenbank zu aktualisieren.

### <a name="the-command-class"></a>Die Befehlsklasse

Ein Befehl ist eine Anforderung für das System zum Ausführen einer Aktion, die den Zustand des Systems ändert. Befehle sind imperativ und sollten nur einmal verarbeitet werden.

Befehle sind zwingende Erfordernisse, werden in der Regel mit einem Verb im Infinitiv gebildet (z.B. „Erstellen“ oder „Aktualisieren“) und können den Aggregattyp, z.B. CreateOrderCommand, enthalten. Anders als ein Ereignis ist ein Befehl kein Fakt aus der Vergangenheit, sondern nur eine Anforderung, die auch abgelehnt werden kann.

Befehle können ihren Ursprung in der Benutzeroberfläche als Ergebnis einer Initiierung einer Anforderung durch einen Benutzer oder von einem Prozess-Manager haben, der ein Aggregat zum Ausführen einer Aktion weiterleitet.

Ein wichtiges Merkmal eines Befehls ist, dass er nur einmal von einem einzelnen Empfänger verarbeitet werden soll. Dies ist darauf zurückzuführen, dass der Befehl eine einzelne Aktion oder Transaktion ist, die Sie in der Anwendung durchführen möchten. Beispielsweise sollte ein Bestellungserstellungsbefehl nur einmal ausgeführt werden. Dies ist ein wichtiger Unterschied zwischen Befehlen und Ereignissen. Ereignisse können mehrmals verarbeitet werden, da viele Systeme oder Microservices am Ereignis interessiert sein können.

Darüber hinaus ist es wichtig, dass ein Befehl für den Fall, dass er nicht idempotent ist, nur einmal verarbeitet werden kann. Ein Befehl ist idempotent, wenn er mehrere Male ausgeführt werden kann, ohne das Ergebnis entweder aufgrund der Art des Befehls oder aufgrund der Art und Weise, wie das System den Befehl behandelt, zu ändern.

Es wird empfohlen, Befehle und Updates, sofern dies nach den Geschäftsregeln und Invarianten Ihrer Domäne sinnvoll erscheint, idempotent zu implementieren. Um das gleiche Beispiel zu verwenden: Wenn der gleiche CreateOrder-Befehl aus einem beliebigen Grund (Wiederholungslogik, Hacker usw.) Ihr System mehrmals erreicht, sollten Sie in der Lage sein, ihn zu identifizieren und sicherzustellen, dass nicht mehrere Bestellungen erstellt werden. Zu diesem Zweck müssen Sie ein Art von Identität in den Vorgängen anfügen und feststellen, ob der Befehl oder das Update bereits verarbeitet wurde.

Sie senden einen Befehl an einen einzelnen Empfänger, d.h. Sie veröffentlichen einen Befehl nicht. Die Veröffentlichung wendet sich an Ereignisse, die einen Fakt anführen, z.B. dass etwas passiert ist und dass dies für Ereignisempfänger interessant sein kann. Im Fall von Ereignissen spielt es für den Verleger keine Rolle, welche Empfänger das Ereignis erhalten oder wie sie es verwenden. Mit Domänen- oder Integrationsereignissen verhält es sich jedoch anders, wie bereits in vorherigen Abschnitten vorgestellt.

Ein Befehl ist mit einer Klasse implementiert, die Datenfelder oder Sammlungen mit allen Informationen enthält, die benötigt werden, um diesen Befehl auszuführen. Ein Befehl ist eine besondere Art von Data Transfer Object (DTO), das speziell zum Anfordern von Änderungen oder Transaktionen verwendet wird. Der Befehl selbst basiert auf genau den Informationen, die für die Verarbeitung des Befehls erforderlich sind.

Das folgende Beispiel zeigt die vereinfachte `CreateOrderCommand`-Klasse. Dies ist ein unveränderlicher-Befehl, der in dem Microservice für Bestellung in eShopOnContainers verwendet wird.

```csharp
// DDD and CQRS patterns comment: Note that it is recommended to implement immutable Commands
// In this case, its immutability is achieved by having all the setters as private
// plus only being able to update the data just once, when creating the object through its constructor.
// References on Immutable Commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://docs.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties

[DataContract]
public class CreateOrderCommand
    : IRequest<bool>
{
    [DataMember]
    private readonly List<OrderItemDTO> _orderItems;

    [DataMember]
    public string UserId { get; private set; }

    [DataMember]
    public string UserName { get; private set; }

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

    public CreateOrderCommand(List<BasketItem> basketItems, string userId, string userName, string city, string street, string state, string country, string zipcode,
        string cardNumber, string cardHolderName, DateTime cardExpiration,
        string cardSecurityNumber, int cardTypeId) : this()
    {
        _orderItems = basketItems.ToOrderItemsDTO().ToList();
        UserId = userId;
        UserName = userName;
        City = city;
        Street = street;
        State = state;
        Country = country;
        ZipCode = zipcode;
        CardNumber = cardNumber;
        CardHolderName = cardHolderName;
        CardExpiration = cardExpiration;
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

Die Befehlsklasse enthält im Grunde die zum Ausführen einer Geschäftstransaktion mithilfe der Domänenmodellobjekte benötigten Daten. Daher sind die Befehle einfach Datenstrukturen, die schreibgeschützte Daten und kein Verhalten enthalten. Der Name des Befehls gibt seinen Zweck an. In vielen Sprachen, z.B. in C#, werden Befehle als Klassen dargestellt, sind aber keine echten Klassen im objektorientierten Sinn.

Befehle haben eine zusätzliche Eigenschaft, d.h. sie sind unveränderlich, da erwartet wird, dass sie direkt vom Domänenmodell verarbeitet werden. Sie müssen während ihrer projizierten Lebensdauer nicht geändert werden. In einer C#-Klasse kann Unveränderlichkeit dadurch erreicht werden, dass keine Setter oder andere Methoden verwendet werden, die den internen Status ändern.

Beachten Sie, dass zum Durchlaufen des Serialisierungs-/Deserialisierungsprozesses durch Befehle die Eigenschaften den Setter „privat“ und das Attribut `[DataMember]` (oder `[JsonProperty]`) erfordern. Andernfalls kann der Deserialisierer das Objekt im Ziel nicht mit den erforderlichen Werten rekonstruieren. Sie können auch tatsächlich schreibgeschützte Eigenschaften verwenden, wenn die Klasse einen Konstruktor mit Parametern für alle Eigenschaften mit der üblichen camelCase-Benennungskonvention hat, und den Konstruktor mit `[JsonConstructor]` kommentieren. Diese Option erfordert jedoch mehr Code.

Die Befehlsklasse zum Erstellen einer Bestellung beispielsweise ist möglicherweise im Hinblick auf Daten der Bestellung ähnlich, die Sie erstellen möchten, aber Sie benötigen wahrscheinlich nicht die gleichen Attribute. Beispielsweise enthält `CreateOrderCommand` keine Bestell-ID, da die Bestellung noch nicht erstellt wurde.

Viele Befehlsklassen können einfach sein und nur wenige Felder über einen Zustand erfordern, der geändert werden muss. Das wäre der Fall, wenn Sie nur den Status einer Bestellung von „In Bearbeitung“ in „Bezahlt“ oder „Geliefert“ ändern, indem Sie einen Befehl wie den Folgenden verwenden:

```csharp
[DataContract]
public class UpdateOrderStatusCommand
    :IRequest<bool>
{
    [DataMember]
    public string Status { get; private set; }

    [DataMember]
    public string OrderId { get; private set; }

    [DataMember]
    public string BuyerIdentityGuid { get; private set; }
}
```

Einige Entwickler trennen ihre Benutzeroberflächen-Anforderungsobjekte von den Befehls-DTOs, was jedoch eine „Geschmacksfrage“ ist. Die Trennung ist zeitraubend und nur mit geringem Mehrwert verbunden, und die Form der Objekte ist nahezu identisch. In eShopOnContainers beispielsweise stammen einige Befehle direkt vom Client.

### <a name="the-command-handler-class"></a>Die Befehlshandler-Klasse

Sie sollten für jeden Befehl eine bestimmte Befehlshandler-Klasse implementieren. Sie gibt vor, wie das Muster funktioniert, und ist der Ort, an dem Sie das Befehlsobjekt, die Domänenobjekte und die Repositoryobjekte der Infrastruktur verwenden. Der Befehlshandler ist das Herzstück der Anwendungsschicht im Hinblick auf CQRS und DDD. Allerdings sollte die Domänenlogik in den Domänenklassen enthalten sein, und zwar in den aggregierten Stämmen (Stammentitäten), untergeordneten Entitäten oder [Domänendiensten](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), aber nicht im Befehlshandler, der eine Klasse der Anwendungsschicht ist.

Die Befehlshandlerklasse eignet sich ideal zum Erreichen bereits erwähnten Prinzips der einzigen Verantwortung.

Ein Befehlshandler empfängt einen Befehl und erhält ein Ergebnis aus dem Aggregat, das verwendet wird. Das Ergebnis sollte die erfolgreiche Ausführung des Befehls oder eine Ausnahme sein. Im Falle einer Ausnahme sollte der Systemstatus nicht geändert werden.

In den Befehlshandler fließen normalerweise die folgenden Schritte ein:

- Er empfängt das Befehlsobjekt wie ein DTO (aus dem [Vermittler](https://en.wikipedia.org/wiki/Mediator_pattern)- oder einem anderen Infrastrukturobjekt).

- Er überprüft, ob der Befehl (sofern nicht durch den Vermittler überprüft) gültig ist.

- Er instanziiert die Aggregatstamminstanz, die das Ziel des aktuellen Befehls ist.

- Sie führt die Methode für die Aggregatsstamminstanz aus und erhält dabei die erforderlichen Daten vom Befehl.

- Sie behält den neuen Zustand des Aggregats in Bezug auf die zugehörige Datenbank bei. Dieser letzte Vorgang ist die eigentliche Transaktion.

Normalerweise befasst sich der Befehlshandler mit einem einzelnen Aggregat, das von seinem Aggregatstamm (Stammentität) gesteuert wird. Wenn mehrere Aggregate vom Empfang eines einzelnen Befehls betroffen sein sollen, können Sie mit den Domänenereignissen Status oder Aktionen über mehrere Aggregate weitergeben.

Wichtig dabei ist, dass sich die Domänenlogik bei der Verarbeitung eines Befehls im Domänenmodell (Aggregat) befinden, vollständig gekapselt und bereit für die Komponententests sein soll. Befehlshandler sind lediglich eine Möglichkeit, um das Domänenmodell aus der Datenbank abzurufen und zum Schluss die Infrastrukturschicht (Repositorys) anzuweisen, die Änderungen beizubehalten, wenn das Modell geändert wird. Der Vorteil dieses Ansatzes ist, dass Sie die Domänenlogik in ein isoliertes, vollständig gekapseltes, umfangreiches, verhaltensbasiertes Domänenmodell umgestalten können, ohne Code in der Anwendung oder in Infrastrukturschichten zu ändern, die die Grundstruktur (Befehlshandler, Web-API, Repositorys usw.) bilden.

Wenn Befehlshandler komplex werden und mit zu viel Logik einhergehen, kann dies zu schlecht strukturiertem Code führen. Überprüfen Sie sie. Wenn Sie Domänenlogik finden, gestalten Sie den Code um, um dieses Domänenverhalten auf die Methoden der Domänenobjekte (Aggregatstamm und untergeordnete Entität) zu übertragen.

Der folgende Code zeigt als Beispiel einer Befehlshandlerklasse die gleiche `CreateOrderCommandHandler`-Klasse, die Sie bereits am Anfang des Kapitels gesehen haben. In diesem Fall werden auch die Handle-Methode und die Vorgänge mit den Domänenmodellobjekten und -aggregaten hervorgehoben.

```csharp
public class CreateOrderCommandHandler
        : IRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;
    private readonly IOrderingIntegrationEventService _orderingIntegrationEventService;
    private readonly ILogger<CreateOrderCommandHandler> _logger;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
        IOrderingIntegrationEventService orderingIntegrationEventService,
        IOrderRepository orderRepository,
        IIdentityService identityService,
        ILogger<CreateOrderCommandHandler> logger)
    {
        _orderRepository = orderRepository ?? throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ?? throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ?? throw new ArgumentNullException(nameof(mediator));
        _orderingIntegrationEventService = orderingIntegrationEventService ?? throw new ArgumentNullException(nameof(orderingIntegrationEventService));
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
    }

    public async Task<bool> Handle(CreateOrderCommand message, CancellationToken cancellationToken)
    {
        // Add Integration event to clean the basket
        var orderStartedIntegrationEvent = new OrderStartedIntegrationEvent(message.UserId);
        await _orderingIntegrationEventService.AddAndSaveEventAsync(orderStartedIntegrationEvent);

        // Add/Update the Buyer AggregateRoot
        // DDD patterns comment: Add child entities and value-objects through the Order Aggregate-Root
        // methods and constructor so validations, invariants and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State, message.Country, message.ZipCode);
        var order = new Order(message.UserId, message.UserName, address, message.CardTypeId, message.CardNumber, message.CardSecurityNumber, message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice, item.Discount, item.PictureUrl, item.Units);
        }

        _logger.LogInformation("----- Creating Order - Order: {@Order}", order);

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync(cancellationToken);
    }
}
```

Hierbei handelt es sich um zusätzliche Schritte, die ein Befehlshandler ausführen sollte:

- Verwenden Sie die Daten des Befehls für Arbeit mit den Methoden und dem Verhalten des Aggregatstamms.

- Lösen Sie intern in den Domänenobjekten Domänenereignisse aus, während die Transaktion ausgeführt wird, was aus der Sicht des Befehlshandlers transparent ist.

- Wenn das Vorgangsergebnis des Aggregats erfolgreich und die Transaktion beendet ist, lösen Sie Integrationsereignisse aus. (Diese können auch von Infrastrukturklassen wie Repositorys ausgelöst werden.)

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Mark Seemann. At the Boundaries, Applications are Not Object-Oriented (An den Grenzen sind Anwendungen nicht objektorientiert)**  \
  <https://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/>

- **Commands and events (Befehle und Ereignisse)**  \
  <https://cqrs.nu/Faq/commands-and-events>

- **What does a command handler do? (Wie funktioniert ein Befehlshandler?)** \
  <https://cqrs.nu/Faq/command-handlers>

- **Jimmy Bogard. Domain Command Patterns – Handlers (Domänenbefehlsmuster – Handler)**  \
  <https://jimmybogard.com/domain-command-patterns-handlers/>

- **Jimmy Bogard. Domain Command Patterns – Validation (Domänenbefehlsmuser – Prüfung)**  \
  <https://jimmybogard.com/domain-command-patterns-validation/>

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a>Die Befehlsprozesspipeline: So wird ein Befehlshandler ausgelöst

Die nächste Frage lautet, wie ein Befehlshandler aufgerufen wird. Sie können ihn manuell über jeden zugehörigen ASP.NET Core-Controller aufrufen. Der Ansatz wäre allerdings zu sehr gekoppelt und ist nicht ideal.

Die anderen beiden Hauptoptionen, die empfohlen werden, lauten:

- Über ein In-Memory-Vermittlermusterartefakt.

- Mit einer asynchronen Nachrichtenwarteschlange zwischen Controllern und Handlern.

### <a name="use-the-mediator-pattern-in-memory-in-the-command-pipeline"></a>Verwenden von Vermittlermustern (In-Memory) in der Befehlspipeline

Wie in Abbildung 7-25 dargestellt, verwenden Sie in einem CQRS-Ansatz einen intelligenten Vermittler, ähnlich einem In-Memory-Bus. Dieser ist ausreichend intelligent, um den richtigen Befehlshandler basierend auf dem empfangenen Befehlstyp oder dem DTO (Datentransferobjekt) umzuleiten. Die schwarzen Pfeile zwischen Komponenten stellen die Abhängigkeiten zwischen Objekten (in vielen Fällen mit DI eingefügt) mit den zugehörigen Interaktionen dar.

![Diagramm, das eine detailliertere Übersicht über den Datenfluss vom Client zur Datenbank zeigt.](./media/microservice-application-layer-implementation-web-api/mediator-cqrs-microservice.png)

**Abbildung 7-25**. Verwenden des Vermittlermusters in einem CQRS-Microservice

Das obige Diagramm zeigt eine Vergrößerung der Abbildung 7–24: Der ASP.NET Core-Controller sendet den Befehl an die Befehlspipeline von MediatR, damit er zum entsprechenden Handler gelangt.

Die Verwendung des Vermittlermusters ist sinnvoll, da Verarbeitungsanforderungen in Unternehmensanforderungen kompliziert sein können. Sie möchten eine offene Anzahl von querschnittlichen Belangen wie Protokollierung, Überprüfungen, Überwachung und Sicherheit hinzufügen können. In diesen Fällen können Sie auf eine Vermittlerpipeline zurückgreifen (weitere Informationen finden Sie unter [Vermittlermuster](https://en.wikipedia.org/wiki/Mediator_pattern)), um ein Mittel für diese zusätzlichen Verhaltensweisen oder querschnittlichen Belange bereitzustellen.

Ein Vermittler ist ein Objekt, dass das „wie“ dieses Prozesses kapselt: Er koordiniert die Ausführung basierend auf dem Status, der Art und Weise, wie ein Befehlshandler aufgerufen wird, oder der Nutzlast, die Sie dem Handler bereitstellen. Mit einer Vermittlerkomponente können Sie querschnittliche Belange zentral und transparent anwenden, indem Sie von Decorator-Elemente (oder [Pipeline-Verhaltensweisen](https://github.com/jbogard/MediatR/wiki/Behaviors) seit [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)) anwenden. Weitere Informationen finden Sie unter [Decorator pattern (Decorator-Muster)](https://en.wikipedia.org/wiki/Decorator_pattern).

Decorator-Elemente und Verhaltensweisen ähneln der [Aspect Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), werden aber nur auf eine bestimmte Prozesspipeline angewendet, die von der Vermittlerkomponente verwaltet wird. Aspekte in AOP, die übergreifende Anliegen implementieren, werden basierend auf *Aspect Weavers* angewendet, die zum Zeitpunkt der Kompilierung oder basierend auf einer Objektaufruf-Interception eingefügt werden. Über die beiden typischen AOP-Ansätze wird gesagt, dass sie wie „Zauberei“ funktionieren, da es nicht einfach ist nachzuvollziehen, wie AOP seine Aufgabe erledigt. Beim Umgang mit schwerwiegenden Problemen oder Fehlern kann das Debuggen von AOP schwierig sein. Da diese Decorator-Elemente/Verhaltensweisen andererseits explizit sind und nur im Rahmen des Vermittlers angewendet werden, ist das Debuggen wesentlich besser vorhersagbar und einfach.

Im Microservice für Bestellung von eShopOnContainers sind beispielsweise zwei Musterverhalten implementiert: eine [LogBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs)-Klasse und eine [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs)-Klasse. Die Implementierung von Verhalten wird im nächsten Abschnitt erläutert. Dort wird erklärt, wie eShopOnContainers die [MediatR](https://www.nuget.org/packages/MediatR)-[Verhalten](https://github.com/jbogard/MediatR/wiki/Behaviors) verwendet.

### <a name="use-message-queues-out-of-proc-in-the-commands-pipeline"></a>Verwenden von Nachrichtenwarteschlangen (prozessextern) in der Befehlspipeline

Eine andere Möglichkeit ist die Verwendung asynchroner Nachrichten basierend auf Brokern oder Nachrichtenwarteschlagen (s. Abbildung 7-26). Diese Option kann auch mit der Vermittlerkomponente direkt vor dem Befehlshandler kombiniert werden.

![Diagramm, das den Datenfluss unter Verwendung einer Hochverfügbarkeits-Nachrichtenwarteschlange zeigt.](./media/microservice-application-layer-implementation-web-api/add-ha-message-queue.png)

**Abbildung 7-26**. Verwenden von Nachrichtenwarteschlangen (prozessexterne und prozessübergreifende Kommunikation) mit CQRS-Befehlen

Die Befehlspipeline kann auch über eine hochverfügbare Nachrichtenwarteschlange verarbeitet werden, um die Befehle an den entsprechenden Handler zu übergeben. Wenn Nachrichtenwarteschlangen verwendet werden, um die Befehle zu akzeptieren, kann die Pipeline des Befehls noch komplexer werden, da Sie sie wahrscheinlich in zwei über die externe Warteschlange verbundene Prozesse aufteilen müssen. Die Verwendung ist jedoch sinnvoll, wenn Sie Skalierbarkeit und Leistung basierend auf asynchronem Messaging verbessern müssen. Beachten Sie, dass im Fall von Abbildung 7-26 der Controller nur die Befehlsnachricht in die Warteschlange sendet und zurückgibt. Die Befehlshandler verarbeiten die Nachrichten in ihrem eigenen Tempo. Dies ist ein großer Vorteil von Warteschlangen: Die Nachrichtenwarteschlange kann als Puffer fungieren, wenn Hyperskalierbarkeit erforderlich ist, z.B. für Lager oder jedes andere Szenario mit einem hohen eingehenden Datenaufkommen.

Da die Nachrichtenwarteschlangen asynchron sind, müssen Sie herausfinden, wie die Clientanwendung über den Erfolg oder Misserfolg des Befehlsprozesses informiert werden soll. Im Allgemeinen sollten Sie nie „Fire and Forget“-Befehle verwenden. Jede Geschäftsanwendung muss wissen, ob ein Befehl erfolgreich verarbeitet oder zumindest überprüft und akzeptiert wurde.

Die Komplexität Ihres Systems wird erhöht, da nach dem Validieren einer Befehlsnachricht, die an eine asynchrone Warteschlange übermittelt wurde, auf den Client reagiert werden kann, während ein prozessinterner Befehl das Ergebnis des Befehls nach der Ausführung der Transaktion zurückgibt. Bei Verwendung von Warteschlangen, müssen Sie möglicherweise das Ergebnis des Befehlsprozesses über andere Vorgangsergebnismeldungen zurückgeben, wofür zusätzliche Komponenten und eine benutzerdefinierte Kommunikation in Ihrem System benötigt werden.

Darüber hinaus sind asynchrone Befehle unidirektionale Befehle, die jedoch in vielen Fällen möglicherweise nicht benötigt werden, was in der folgenden interessanten [Online-Unterhaltung](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ) zwischen Burtsev Alexey und Greg Young erläutert wird:

> \[Burtsev Alexey\] Ich finde häufig Code, in dem grundlos asynchrone Befehlsbehandlung oder unidirektionales Befehlsmessaging verwendet wird (es handelt sich nicht um einen langen Vorgang, es wird kein externer asynchroner Code ausgeführt, es handelt sich noch nicht einmal um anwendungsübergreifende Grenzen für die Verwendung des Nachrichtenbusses). Wozu diese unnötige Komplexität? Und ich habe bisher noch kein CQRS-Codebeispiel mit blockierendem Befehlshandler gesehen, obwohl dieser in den meisten Fällen gut geeignet ist.
>
> \[Greg Young\] \[...\] ein asynchroner Befehl ist nicht vorhanden. Es handelt sich eigentlich um ein anderes Ereignis. Wenn ich das akzeptieren, was Sie mir senden, und ein Ereignis auslösen muss, wenn ich nicht zustimme, weisen Sie mich nicht dazu an etwas zu tun, \[d. h., es handelt sich um keinen Befehl\]. Man informiert mich vielmehr darüber, dass etwas getan wurde. Auf den ersten Blick scheint es sich um einen geringfügigen Unterschied zu handeln, aber er hat viele Auswirkungen.

Asynchrone Befehle erhöhen die Komplexität eines Systems entscheidend, da es keine einfache Möglichkeit gibt, Fehler anzuzeigen. Daher werden asynchrone Befehle nur dann empfohlen, wenn Skalierungsanforderungen erforderlich sind, oder aber in besonderen Fällen für die Kommunikation von internen Microservices über Messaging. In diesen Fällen müssen Sie ein eigenes Reporting- und Wiederherstellungssystem für Fehler entwickeln.

Bei der ursprünglichen Version von eShopOnContainers wurde die Verwendung der synchronen Befehlsverarbeitung beschlossen, die von HTTP-Anforderungen ausgeht und von Vermittlermustern gesteuert wird. Auf diese Weise kann der Erfolg oder Misserfolg des Prozesses wie in der [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/netcore1.1/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs)-Implementierung zurückgegeben werden.

In jedem Fall sollte diese Entscheidung auf der Grundlage der geschäftlichen Anforderung Ihrer Anwendung oder Ihres Microservices getroffen werden.

## <a name="implement-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a>Implementieren der Befehlsprozesspipeline mit einem Vermittlermuster (MediatR)

Als Beispielimplementierung wird in dieser Anleitung die Verwendung der prozessinternen Pipeline basierend auf dem Vermittlermuster vorgeschlagen, um im Speicher die Befehlserfassung zu steuern und Befehle an die richtigen Befehlshandler weiterzuleiten. In der Anleitung wird außerdem die Anwendung von [Verhaltensweisen](https://github.com/jbogard/MediatR/wiki/Behaviors) vorgeschlagen, um querschnittliche Belange abzutrennen.

Für die Implementierung in .NET sind mehrere Open-Source-Bibliotheken verfügbar sind, die das Vermittlermuster implementieren. In dieser Anleitung wird die Open-Source-Bibliothek [MediatR](https://github.com/jbogard/MediatR) verwendet (von Jimmy Bogard erstellt), aber Sie können auch einen anderen Ansatz verwenden. MediatR ist eine kleine und einfache-Bibliothek, die Ihnen ermöglicht, die In-Memory-Nachrichten, z.B. einen Befehl, zu verarbeiten, während Sie Decorator-Elemente oder Verhaltensweisen anwenden.

Mithilfe des Vermittlermusters können Sie die Kopplung reduzieren und mit den angeforderten Aufgaben verbundene Bedenken isolieren, während automatisch eine Verbindung mit dem Handler herstellt wurde, der die Aufgaben ausführt - in diesem Fall mit Befehlshandlern.

Ein weiterer guter Grund für die Verwendung des Musters wurde von Jimmy Bogard erläutert, als er die vorliegende Anleitung überprüfte:

> An dieser Stelle sollten auch Tests erwähnt werden. Sie bieten einen interessanten und konsistenten Einblick in das Verhalten des Systems. Eingabe der Anforderung , Ausgabe der Antwort. Dieser Aspekt war eine wichtige Voraussetzung für die Entwicklung von Tests mit durchgängigem Verhalten.

Zunächst wird ein WebAPI-Beispielcontroller behandelt, auf dem Sie normalerweise das Vermittlerobjekt verwenden. Wenn Sie das Vermittlerobjekt nicht verwenden würden, müssten Sie alle Abhängigkeiten für diesen Controller einfügen, etwa ein Protokollierungsobjekt usw. Das Ergebnis wäre ein komplizierter Konstruktor. Wenn Sie jedoch das Vermittlerobjekt verwenden, kann der Konstruktor des Controllers wesentlich einfacher sein, mit einigen wenigen Abhängigkeiten anstelle von vielen Abhängigkeiten, z.B. eine pro querschnittlichen Vorgang, was im folgenden Beispiel veranschaulicht wird:

```csharp
public class MyMicroserviceController : Controller
{
    public MyMicroserviceController(IMediator mediator,
                                    IMyMicroserviceQueries microserviceQueries)
    {
        // ...
    }
}
```

Wie Sie sehen, stellt der Vermittler einen übersichtlichen und schlanken Web-API-Controllerkonstruktor bereit. Darüber hinaus nimmt der Code zum Senden eines Befehls an das Vermittlerobjekt in dem Controllermethoden fast eine Zeile ein:

```csharp
[Route("new")]
[HttpPost]
public async Task<IActionResult> ExecuteBusinessOperation([FromBody]RunOpCommand
                                                               runOperationCommand)
{
    var commandResult = await _mediator.SendAsync(runOperationCommand);

    return commandResult ? (IActionResult)Ok() : (IActionResult)BadRequest();
}
```

### <a name="implement-idempotent-commands"></a>Implementieren von idempotenten Befehlen

**eShopOnContainers** enthält ein komplexeres Beispiel als das oben aufgeführte. Es veranschaulicht die Übermittlung eines CreateOrderCommand-Objekts aus dem Microservice für Bestellungen. Aber da der Bestellgeschäftsprozess etwas komplexer ist und im vorliegenden Fall am Warenkorbmicroservice beginnt, wird die Aktion „Übermittlung“ des CreateOrderCommand-Objekts von einem Integrationsereignishandler namens [UserCheckoutAcceptedIntegrationEventHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) und nicht von einem einfachen WebAPI-Controller ausgeführt, der wie in dem vorherigen, einfacheren Verfahren von der Client-App aufgerufen wird.

Die Aktion der Übermittlung des Befehls an MediatR ist, wie im folgenden Code veranschaulicht, relativ ähnlich.

```csharp
var createOrderCommand = new CreateOrderCommand(eventMsg.Basket.Items,
                                                eventMsg.UserId, eventMsg.City,
                                                eventMsg.Street, eventMsg.State,
                                                eventMsg.Country, eventMsg.ZipCode,
                                                eventMsg.CardNumber,
                                                eventMsg.CardHolderName,
                                                eventMsg.CardExpiration,
                                                eventMsg.CardSecurityNumber,
                                                eventMsg.CardTypeId);

var requestCreateOrder = new IdentifiedCommand<CreateOrderCommand,bool>(createOrderCommand,
                                                                        eventMsg.RequestId);
result = await _mediator.Send(requestCreateOrder);
```

Dieser Fall ist jedoch auch etwas anspruchsvoller, da idempotente Befehle implementiert werden. Der CreateOrderCommand-Prozess sollte idempotent sein. Wenn eine Nachricht aus einem beliebigen Grund, z.B. bei Neuversuchen, dupliziert im Netzwerk übermittelt wird, wird der gleiche Geschäftsauftrag nur einmal verarbeitet.

Dies wird durch Umschließen des Geschäftsbefehls (hier CreateOrderCommand) und Einbettung in einen generischen IdentifiedCommand implementiert, der von einer ID jeder Nachricht über das Netzwerk verfolgt wird, das idempotent sein muss.

Im folgenden Code können Sie sehen, dass der IdentifiedCommand nichts weiter als eine DTO mit ID sowie das umschlossene Geschäftsbefehlsobjekt ist.

```csharp
public class IdentifiedCommand<T, R> : IRequest<R>
    where T : IRequest<R>
{
    public T Command { get; }
    public Guid Id { get; }
    public IdentifiedCommand(T command, Guid id)
    {
        Command = command;
        Id = id;
    }
}
```

Anschließend prüft der CommandHandler für den IdentifiedCommand namens [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs) grundsätzlich, ob die als Teil der Nachricht ankommende ID bereits in einer Tabelle vorhanden ist. Wenn sie bereits vorhanden ist, wird der Befehl nicht noch einmal verarbeitet und verhält sich wie ein idempotenter Befehl. Der Infrastrukturcode wird durch den unten stehenden Methodenaufruf `_requestManager.ExistAsync` ausgeführt.

```csharp
// IdentifiedCommandHandler.cs
public class IdentifiedCommandHandler<T, R> : IRequestHandler<IdentifiedCommand<T, R>, R>
        where T : IRequest<R>
{
    private readonly IMediator _mediator;
    private readonly IRequestManager _requestManager;
    private readonly ILogger<IdentifiedCommandHandler<T, R>> _logger;

    public IdentifiedCommandHandler(
        IMediator mediator,
        IRequestManager requestManager,
        ILogger<IdentifiedCommandHandler<T, R>> logger)
    {
        _mediator = mediator;
        _requestManager = requestManager;
        _logger = logger ?? throw new System.ArgumentNullException(nameof(logger));
    }

    /// <summary>
    /// Creates the result value to return if a previous request was found
    /// </summary>
    /// <returns></returns>
    protected virtual R CreateResultForDuplicateRequest()
    {
        return default(R);
    }

    /// <summary>
    /// This method handles the command. It just ensures that no other request exists with the same ID, and if this is the case
    /// just enqueues the original inner command.
    /// </summary>
    /// <param name="message">IdentifiedCommand which contains both original command & request ID</param>
    /// <returns>Return value of inner command or default value if request same ID was found</returns>
    public async Task<R> Handle(IdentifiedCommand<T, R> message, CancellationToken cancellationToken)
    {
        var alreadyExists = await _requestManager.ExistAsync(message.Id);
        if (alreadyExists)
        {
            return CreateResultForDuplicateRequest();
        }
        else
        {
            await _requestManager.CreateRequestForCommandAsync<T>(message.Id);
            try
            {
                var command = message.Command;
                var commandName = command.GetGenericTypeName();
                var idProperty = string.Empty;
                var commandId = string.Empty;

                switch (command)
                {
                    case CreateOrderCommand createOrderCommand:
                        idProperty = nameof(createOrderCommand.UserId);
                        commandId = createOrderCommand.UserId;
                        break;

                    case CancelOrderCommand cancelOrderCommand:
                        idProperty = nameof(cancelOrderCommand.OrderNumber);
                        commandId = $"{cancelOrderCommand.OrderNumber}";
                        break;

                    case ShipOrderCommand shipOrderCommand:
                        idProperty = nameof(shipOrderCommand.OrderNumber);
                        commandId = $"{shipOrderCommand.OrderNumber}";
                        break;

                    default:
                        idProperty = "Id?";
                        commandId = "n/a";
                        break;
                }

                _logger.LogInformation(
                    "----- Sending command: {CommandName} - {IdProperty}: {CommandId} ({@Command})",
                    commandName,
                    idProperty,
                    commandId,
                    command);

                // Send the embedded business command to mediator so it runs its related CommandHandler
                var result = await _mediator.Send(command, cancellationToken);

                _logger.LogInformation(
                    "----- Command result: {@Result} - {CommandName} - {IdProperty}: {CommandId} ({@Command})",
                    result,
                    commandName,
                    idProperty,
                    commandId,
                    command);

                return result;
            }
            catch
            {
                return default(R);
            }
        }
    }
}
```

Der IdentifiedCommand-Befehl verhält sich wie der Umschlag eines Geschäftsbefehls. Wenn der Geschäftsbefehl verarbeitet werden muss, da er keine wiederholte ID ist, wird der innere Geschäftsbefehl wie im letzten Teil des oben stehenden Codes bei Ausführung von `_mediator.Send(message.Command)` über [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs) erneut an den Vermittler übermittelt.

Dabei wird der Geschäftsbefehlshandler verlinkt und ausgeführt. In diesem Fall handelt es sich um den [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs), der – wie im folgenden Code gezeigt – Transaktionen für die Bestellungsdatenbank ausführt.

```csharp
// CreateOrderCommandHandler.cs
public class CreateOrderCommandHandler
        : IRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;
    private readonly IOrderingIntegrationEventService _orderingIntegrationEventService;
    private readonly ILogger<CreateOrderCommandHandler> _logger;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
        IOrderingIntegrationEventService orderingIntegrationEventService,
        IOrderRepository orderRepository,
        IIdentityService identityService,
        ILogger<CreateOrderCommandHandler> logger)
    {
        _orderRepository = orderRepository ?? throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ?? throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ?? throw new ArgumentNullException(nameof(mediator));
        _orderingIntegrationEventService = orderingIntegrationEventService ?? throw new ArgumentNullException(nameof(orderingIntegrationEventService));
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
    }

    public async Task<bool> Handle(CreateOrderCommand message, CancellationToken cancellationToken)
    {
        // Add Integration event to clean the basket
        var orderStartedIntegrationEvent = new OrderStartedIntegrationEvent(message.UserId);
        await _orderingIntegrationEventService.AddAndSaveEventAsync(orderStartedIntegrationEvent);

        // Add/Update the Buyer AggregateRoot
        // DDD patterns comment: Add child entities and value-objects through the Order Aggregate-Root
        // methods and constructor so validations, invariants and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State, message.Country, message.ZipCode);
        var order = new Order(message.UserId, message.UserName, address, message.CardTypeId, message.CardNumber, message.CardSecurityNumber, message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice, item.Discount, item.PictureUrl, item.Units);
        }

        _logger.LogInformation("----- Creating Order - Order: {@Order}", order);

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync(cancellationToken);
    }
}
```

### <a name="register-the-types-used-by-mediatr"></a>Registrieren der von MediatR verwendeten Typen

Damit MediatR Ihre Befehlshandlerklassen erkennt, müssen Sie die Vermittlerklassen und die Befehlshandlerklassen in Ihrem IoC-Container registrieren. MediatR verwendet standardmäßig Autofac als IoC-Container, aber Sie können auch den integrierten ASP.NET Core-IoC-Container oder einen anderen von MediatR unterstützten Container verwenden.

Im folgenden Code wird veranschaulicht, wie die Typen und Befehle des Vermittlers registriert werden, wenn Autofac-Module verwendet werden.

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(typeof(CreateOrderCommand).GetTypeInfo().Assembly)
                .AsClosedTypesOf(typeof(IRequestHandler<,>));
        // Other types registration
        //...
    }
}
```

Dies ist quasi der Kern von MediatR.

Jeder Befehlshandler implementiert die generische `IRequestHandler<T>`-Schnittstelle. Wenn Sie die Assemblys mit der `RegisteredAssemblyTypes`-Methode registrieren, werden alle als `IRequestHandler` gekennzeichneten Typen auch mit deren `Commands` registriert. Beispiel:

```csharp
public class CreateOrderCommandHandler
  : IRequestHandler<CreateOrderCommand, bool>
{
```

Das ist der Code, der Befehle mit Befehlshandlern korreliert. Der Handler ist nur eine einfache Klasse, aber er erbt vom `RequestHandler<T>` (<T> steht für den Befehlstyp), und MediatR stellt sicher, dass er mit der richtigen Nutzlast aufgerufen wird.

## <a name="apply-cross-cutting-concerns-when-processing-commands-with-the-behaviors-in-mediatr"></a>Anwenden von übergreifenden Belangen beim Verarbeiten von Befehlen mit Verhalten in MediatR

Es gibt zudem die Möglichkeit, querschnittliche Belange auf die Vermittlerpipeline anzuwenden. Sie können auch am Ende des Autofac-Registrierungsmodulcodes sehen, wie ein Verhaltenstyp registriert wird, insbesondere eine benutzerdefinierte LoggingBehavior-Klasse und eine ValidatorBehavior-Klasse. Sie können jedoch auch anderes benutzerdefiniertes Verhalten hinzufügen.

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(
                              typeof(CreateOrderCommand).GetTypeInfo().Assembly).
                                   AsClosedTypesOf(typeof(IRequestHandler<,>));
        // Other types registration
        //...
        builder.RegisterGeneric(typeof(LoggingBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
        builder.RegisterGeneric(typeof(ValidatorBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
    }
}
```

Die [LoggingBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs)-Klasse kann wie der folgende Code implementiert werden, der Informationen über den Befehlshandler, der ausgeführt wird, und über den Erfolg oder Misserfolg der Ausführung protokolliert.

```csharp
public class LoggingBehavior<TRequest, TResponse>
         : IPipelineBehavior<TRequest, TResponse>
{
    private readonly ILogger<LoggingBehavior<TRequest, TResponse>> _logger;
    public LoggingBehavior(ILogger<LoggingBehavior<TRequest, TResponse>> logger) =>
                                                                  _logger = logger;

    public async Task<TResponse> Handle(TRequest request,
                                        RequestHandlerDelegate<TResponse> next)
    {
        _logger.LogInformation($"Handling {typeof(TRequest).Name}");
        var response = await next();
        _logger.LogInformation($"Handled {typeof(TResponse).Name}");
        return response;
    }
}
```

Durch die Implementierung dieser Verhaltensklasse und ihre Registrierung in der Pipeline (im obigen Vermittlermodul) protokollieren alle über MediatR verarbeiteten Befehle Informationen zur Ausführung.

Der Microservice für Bestellung von eShopOnContainers wendet auch ein zweites Verhalten für grundlegende Validierungen an, und zwar die [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs)-Klasse, die auf der Bibliothek [FluentValidation](https://github.com/JeremySkinner/FluentValidation) basiert, wie im folgenden Code dargestellt:

```csharp
public class ValidatorBehavior<TRequest, TResponse>
         : IPipelineBehavior<TRequest, TResponse>
{
    private readonly IValidator<TRequest>[] _validators;
    public ValidatorBehavior(IValidator<TRequest>[] validators) =>
                                                         _validators = validators;

    public async Task<TResponse> Handle(TRequest request,
                                        RequestHandlerDelegate<TResponse> next)
    {
        var failures = _validators
            .Select(v => v.Validate(request))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();

        if (failures.Any())
        {
            throw new OrderingDomainException(
                $"Command Validation Errors for type {typeof(TRequest).Name}",
                        new ValidationException("Validation exception", failures));
        }

        var response = await next();
        return response;
    }
}
```

Hier löst das Verhalten eine Ausnahme aus, wenn die Validierung fehlschlägt. Allerdings können Sie auch ein Ergebnisobjekt zurückgeben, das das Befehlsergebnis enthält, wenn der Befehl erfolgreich ausgeführt wurde, oder andernfalls die Validierungsnachrichten. Dies würde es wahrscheinlich einfacher machen, dem Benutzer die Prüfungsergebnisse anzuzeigen.

Anschließend würden Sie auf der Grundlage der [FluentValidation](https://github.com/JeremySkinner/FluentValidation)-Bibliothek eine Validierung für die mit CreateOrderCommand übergebenen Daten erstellen, was im folgenden Code veranschaulicht wird:

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
        RuleFor(command => command.CardExpiration).NotEmpty().Must(BeValidExpirationDate).WithMessage("Please specify a valid card expiration date");
        RuleFor(command => command.CardSecurityNumber).NotEmpty().Length(3);
        RuleFor(command => command.CardTypeId).NotEmpty();
        RuleFor(command => command.OrderItems).Must(ContainOrderItems).WithMessage("No order items found");
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

Sie können zusätzliche Überprüfungen erstellen. Mit dieser Methode können Sie Befehlsüberprüfungen strukturiert und elegant implementieren.

Auf ähnliche Weise könnten Sie andere Verhaltensweisen für zusätzliche Aspekte oder querschnittliche Belange implementieren, die Sie bei der Behandlung auf Befehle anwenden können.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

##### <a name="the-mediator-pattern"></a>Das Vermittlermuster

- **Vermittlermuster** \
  [https://en.wikipedia.org/wiki/Mediator\_pattern](https://en.wikipedia.org/wiki/Mediator_pattern)

##### <a name="the-decorator-pattern"></a>Das Decorator-Muster

- **Decoratormuster** \
  [https://en.wikipedia.org/wiki/Decorator\_pattern](https://en.wikipedia.org/wiki/Decorator_pattern)

##### <a name="mediatr-jimmy-bogard"></a>MediatR (Jimmy Bogard)

- **MediatR.** GitHub-Repository. \
  <https://github.com/jbogard/MediatR>

- **CQRS with MediatR and AutoMapper (CQRS mit MediatR und AutoMapper)**  \
  <https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/>

- **Put your controllers on a diet: POSTs and commands. (Effiziente Controller: POSTs und Befehle)** \
  <https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/>

- **Tackling cross-cutting concerns with a mediator pipeline (Umgang mit übergreifenden Belangen mithilfe einer Vermittlerpipeline)**  \
  <https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/>

- **CQRS and REST: the perfect match (CQRS und REST: das ideale Paar)**  \
  <https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/>

- **MediatR Pipeline Examples (Beispiele für MediatR-Pipelines)**  \
  <https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/>

- **Vertical Slice Test Fixtures for MediatR and ASP.NET Core (Vertikale Segmenttestfixtures für MediatR und ASP.NET Core)**  \
  <https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>

- **MediatR Extensions for Microsoft Dependency Injection Released (Release: MediatR-Erweiterungen für die Microsoft-Abhängigkeitsinjektion)**  \
  <https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/>

##### <a name="fluent-validation"></a>Fluent-Überprüfung

- **Jeremy Skinner. FluentValidation.** GitHub-Repository. \
  <https://github.com/JeremySkinner/FluentValidation>

> [!div class="step-by-step"]
> [Zurück](microservice-application-layer-web-api-design.md)
> [Weiter](../implement-resilient-applications/index.md)
