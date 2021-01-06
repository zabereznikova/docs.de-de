---
title: Migrieren eines WCF-Anforderungs-/antwortdienstanbieter zu GrpC-GrpC für WCF-Entwickler
description: Erfahren Sie, wie Sie einen einfachen Anforderungs-Antwort-Dienst von WCF zu GrpC migrieren.
ms.date: 12/15/2020
ms.openlocfilehash: 38c6e33e7588dd7c1b263d813d06c088ab484948
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938571"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a>Migrieren eines WCF-Anforderungs-Antwort-Dienstanbieter zu einem unären GrpC-RPC

In diesem Abschnitt wird beschrieben, wie ein einfacher Anforderungs-/Antwort-Dienst in WCF zu einem unären RPC-Dienst in ASP.net Core GrpC migriert wird. Diese Dienste sind die einfachsten Dienst Typen sowohl in Windows Communication Foundation (WCF) als auch in GrpC und sind daher ein hervorragender Ausgangspunkt. Nachdem Sie den Dienst migriert haben, erfahren Sie, wie Sie eine Client Bibliothek aus derselben Datei generieren, `.proto` um den Dienst aus einer .NET-Client Anwendung zu nutzen.

## <a name="the-wcf-solution"></a>Die WCF-Lösung

Die [Projekt](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) Mappe "Projekt Mappe" umfasst einen einfachen Anforderungs-Antwort-Portfolio Dienst zum Herunterladen eines einzelnen Portfolios oder aller Portfolios für einen bestimmten Händler. Der-Dienst wird in der-Schnittstelle `IPortfolioService` mit einem- `ServiceContract` Attribut definiert:

```csharp
[ServiceContract]
public interface IPortfolioService
{
    [OperationContract]
    Task<Portfolio> Get(Guid traderId, int portfolioId);

    [OperationContract]
    Task<List<Portfolio>> GetAll(Guid traderId);
}
```

Das `Portfolio` Modell ist eine einfache c#-Klasse, die mit [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) gekennzeichnet ist und eine Liste von- `PortfolioItem` Objekten einschließt. Diese Modelle werden im `TraderSys.PortfolioData` Projekt zusammen mit einer Repository-Klasse definiert, die eine Datenzugriffs Abstraktion darstellt.

```csharp
[DataContract]
public class Portfolio
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public Guid TraderId { get; set; }

    [DataMember]
    public List<PortfolioItem> Items { get; set; }
}

[DataContract]
public class PortfolioItem
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public int ShareId { get; set; }

    [DataMember]
    public int Holding { get; set; }

    [DataMember]
    public decimal Cost { get; set; }
}
```

Die `ServiceContract` Implementierung verwendet eine Repository-Klasse, die über die Abhängigkeitsinjektion bereitgestellt wird und Instanzen der Typen zurückgibt `DataContract` :

```csharp
public class PortfolioService : IPortfolioService
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }

    public async Task<Portfolio> Get(Guid traderId, int portfolioId)
    {
        return await _repository.GetAsync(traderId, portfolioId);
    }

    public async Task<List<Portfolio>> GetAll(Guid traderId)
    {
        return await _repository.GetAllAsync(traderId);
    }
}
```

## <a name="the-portfoliosproto-file"></a>Die Datei "Portfolios. proto"

Wenn Sie die Anweisungen im vorherigen Abschnitt befolgt haben, sollten Sie ein GrpC-Projekt mit einer `portfolios.proto` Datei haben, die wie folgt aussieht:

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

Der erste Schritt besteht darin, die- `DataContract` Klassen zu ihren protobuf-Entsprechungen zu migrieren.

## <a name="convert-the-datacontract-classes-to-grpc-messages"></a>Konvertieren der DataContract-Klassen in GrpC-Nachrichten

Die- `PortfolioItem` Klasse wird zuerst in eine protobuf-Nachricht konvertiert, da die- `Portfolio` Klasse von ihr abhängt. Die Klasse ist einfach, und drei der Eigenschaften werden direkt den GrpC-Datentypen zugeordnet. Die- `Cost` Eigenschaft, die den für die Freigaben beim Kauf bezahlten Preis darstellt, ist ein `decimal` Feld. GrpC unterstützt nur `float` oder `double` für reelle Zahlen, die nicht für Währungen geeignet sind. Da sich die Freigabe Preise um mindestens einen Cent unterscheiden, können die Kosten als `int32` von Cent ausgedrückt werden.

> [!NOTE]
> Denken Sie daran, `snake_case` für Feldnamen in der Datei zu verwenden `.proto` . Der c#-Code-Generator konvertiert sie in `PascalCase` für Sie, und Benutzer anderer Sprachen werden Ihnen bei der Einhaltung der verschiedenen Codierungsstandards danken.

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

Die `Portfolio` Klasse ist etwas komplizierter. Im WCF-Code hat der Entwickler einen `Guid` für die `TraderId` -Eigenschaft verwendet und enthält eine `List<PortfolioItem>` . In protobuf, die keinen erstklassigen `UUID` Typ hat, sollten Sie ein-Element `string` für das `traderId` -Feld verwenden und es in Ihrem eigenen Code analysieren. Verwenden Sie für die Liste der Elemente das- `repeated` Schlüsselwort für das Feld.

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

Nachdem Sie nun über die Daten Meldungen verfügen, können Sie die RPC-Endpunkte für den Dienst deklarieren.

## <a name="convert-servicecontract-to-a-grpc-service"></a>Konvertieren von ServiceContract in einen GrpC-Dienst

Die WCF `Get` -Methode nimmt zwei Parameter an: `Guid traderId` und `int portfolioId` . GrpC-Dienst Methoden können nur einen einzelnen Parameter verwenden. Daher müssen Sie eine Nachricht erstellen, die die beiden Werte enthält. Es ist üblich, diese Anforderungs Objekte mit dem gleichen Namen wie die Methode, gefolgt vom Suffix, zu benennen `Request` . Auch hier `string` wird für das `traderId` Feld anstelle von verwendet `Guid` .

Der Dienst könnte eine `Portfolio` Nachricht direkt zurückgeben, aber dies kann sich in Zukunft auf die Abwärtskompatibilität auswirken. Es empfiehlt sich `Request` , separate und `Response` Nachrichten für jede Methode in einem Dienst zu definieren, auch wenn viele von Ihnen momentan gleich sind. Deklarieren Sie also eine `GetResponse` Nachricht mit einem einzelnen `Portfolio` Feld.

Dieses Beispiel zeigt die Deklaration der GrpC-Dienst Methode mit der folgenden `GetRequest` Meldung:

```protobuf
message GetRequest {
    string trader_id = 1;
    int32 portfolio_id = 2;
}

message GetResponse {
    Portfolio portfolio = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (GetResponse);
}
```

Die WCF- `GetAll` Methode benötigt nur einen einzigen Parameter, `traderId` , daher kann es vorkommen, dass Sie `string` als Parametertyp angeben könnten. GrpC erfordert jedoch einen definierten Nachrichtentyp. Durch diese Anforderung wird die Verwendung von benutzerdefinierten Nachrichten für alle Eingaben und Ausgaben für zukünftige Abwärtskompatibilität erzwungen.

Die WCF-Methode gibt auch zurück `List<Portfolio>` , aber aus demselben Grund lässt Sie einfache Parametertypen nicht zu, da GrpC nicht `repeated Portfolio` als Rückgabetyp zulässt. Erstellen Sie stattdessen einen `GetAllResponse` Typ, um die Liste zu schließen.

> [!WARNING]
> Möglicherweise sind Sie verlockend, eine `PortfolioList` Nachricht zu erstellen und Sie in mehreren Dienst Methoden zu verwenden, aber Sie sollten dieser Versuchung widerstehen. Es ist nicht möglich, zu wissen, wie sich die verschiedenen Methoden in einem Dienst weiterentwickeln, sodass die Nachrichten spezifisch und ordnungsgemäß getrennt werden.

```protobuf
message GetAllRequest {
    string trader_id = 1;
}

message PortfolioList {
    repeated Portfolio portfolios = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (Portfolio);
    rpc GetAll(GetAllRequest) returns (GetAllResponse);
}
```

Wenn Sie Ihr Projekt mit diesen Änderungen speichern, wird das GrpC-Buildziel im Hintergrund ausgeführt und generiert alle protobuf-Nachrichten Typen und eine Basisklasse, die Sie erben können, um den Dienst zu implementieren.

Öffnen Sie die `Services/GreeterService.cs` -Klasse, und löschen Sie den Beispielcode. Nun können Sie die Portfolio Service-Implementierung hinzufügen. Die generierte Basisklasse befindet sich im `Protos` -Namespace und wird als eine schsted-Klasse generiert. GrpC erstellt eine statische Klasse mit dem gleichen Namen wie der Dienst in der `.proto` Datei und eine Basisklasse mit dem Suffix `Base` innerhalb dieser statischen Klasse, sodass der vollständige Bezeichner für den Basistyp ist `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase` .

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

Die-Basisklasse deklariert `virtual` Methoden für `Get` und `GetAll` , die überschrieben werden können, um den-Dienst zu implementieren. Die Methoden sind `virtual` nicht `abstract` so, dass der Dienst einen expliziten GrpC-Statuscode zurückgeben kann, wenn Sie ihn nicht implementieren, `Unimplemented` ähnlich wie `NotImplementedException` bei einem regulären c#-Code.

Die Signatur für alle unären GrpC-Dienst Methoden in ASP.net Core ist konsistent. Es gibt zwei Parameter: der erste ist der Nachrichtentyp, der in der Datei deklariert ist `.proto` , und der zweite ist eine `ServerCallContext` , die ähnlich wie die `HttpContext` von ASP.net Core funktioniert. Tatsächlich gibt es eine Erweiterungsmethode, `GetHttpContext` die für die- `ServerCallContext` Klasse aufgerufen wird, die Sie verwenden können, um den zugrunde liegenden zu erhalten `HttpContext` , obwohl Sie Sie nicht häufig verwenden müssen. Wir werden uns `ServerCallContext` später in diesem Kapitel und auch im Kapitel, in dem die Authentifizierung erläutert wird, ansehen.

Der Rückgabetyp der Methode ist ein `Task<T>` , wobei `T` der Antwort Nachrichtentyp ist. Alle GrpC-Dienst Methoden sind asynchron.

## <a name="migrate-the-portfoliodata-library-to-net"></a>Migrieren der videodata-Bibliothek zu .net

An diesem Punkt benötigt das Projekt das Portfolio-Repository und die Modelle, die in der `TraderSys.PortfolioData` Klassenbibliothek in der WCF-Lösung enthalten sind. Die einfachste Möglichkeit, Sie zu übernehmen, besteht darin, eine neue Klassenbibliothek zu erstellen, indem Sie entweder das Visual Studio-Dialogfeld " **Neues Projekt** " mit der Vorlage für die Klassenbibliothek (.NET Standard) verwenden, oder über die Befehlszeile in der Befehlszeile, indem Sie .net Core-CLI die folgenden Befehle aus dem Verzeichnis ausführen, das die `TraderSys.sln` Datei enthält:

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

Nachdem Sie die Bibliothek erstellt und der Projekt Mappe hinzugefügt haben, löschen Sie die generierte `Class1.cs` Datei, und kopieren Sie die Dateien aus der Bibliothek der WCF-Projekt Mappe in den Ordner der neuen Klassenbibliothek, wobei die Ordnerstruktur beibehalten wird:

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

.Net-Projekte im SDK-Stil enthalten automatisch alle `.cs` Dateien in oder in Ihrem eigenen Verzeichnis, sodass Sie Sie nicht explizit dem Projekt hinzufügen müssen. Der einzige Schritt besteht darin, das `DataContract` -Attribut und das- `DataMember` Attribut aus den Klassen und zu entfernen, `Portfolio` `PortfolioItem` sodass Sie einfache c#-Klassen sind:

```csharp
public class Portfolio
{
    public int Id { get; set; }
    public Guid TraderId { get; set; }
    public List<PortfolioItem> Items { get; set; }
}

public class PortfolioItem
{
    public int Id { get; set; }
    public int ShareId { get; set; }
    public int Holding { get; set; }
    public decimal Cost { get; set; }
}
```

## <a name="use-aspnet-core-dependency-injection"></a>Verwenden von ASP.net Core-Abhängigkeitsinjektion

Nun können Sie dem GrpC-Anwendungsprojekt einen Verweis auf diese Bibliothek hinzufügen und die `PortfolioRepository` Klasse mithilfe der Abhängigkeitsinjektion in der GrpC-Dienst Implementierung verwenden. In der WCF-Anwendung wurde die Abhängigkeitsinjektion vom autofac IOC-Container bereitgestellt. Die Abhängigkeitsinjektion ASP.net Core wurde in integriert. Sie können das Repository in der- `ConfigureServices` Methode in der- `Startup` Klasse registrieren:

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Register the repository class as a scoped service (instance per request)
        services.AddScoped<IPortfolioRepository, PortfolioRepository>();

        services.AddGrpc();
    }

    // ...
}
```

Die- `IPortfolioRepository` Implementierung kann nun wie folgt als Konstruktorparameter in der-Klasse angegeben werden `PortfolioService` :

```csharp
public class PortfolioService : Protos.Portfolios.PortfoliosBase
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }
}
```

## <a name="implement-the-grpc-service"></a>Implementieren des GrpC-Dienstanbieter

Nachdem Sie die Nachrichten und den Dienst in der Datei deklariert haben `portfolios.proto` , müssen Sie die Dienst Methoden in der Klasse implementieren, `PortfolioService` die von der vom GrpC generierten Klasse erbt `Portfolios.PortfoliosBase` . Die-Methoden werden als `virtual` in der-Basisklasse deklariert. Wenn Sie Sie nicht überschreiben, geben Sie standardmäßig den Statuscode "nicht implementiert" von GrpC zurück.

Beginnen Sie mit der Implementierung der- `Get` Methode. Die Standard Überschreibung sieht wie in diesem Beispiel aus:

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

Das erste Problem ist, dass `request.TraderId` eine Zeichenfolge ist und der Dienst eine erfordert `Guid` . Obwohl das erwartete Format für die Zeichenfolge ist `UUID` , muss der Code die Möglichkeit behandeln, dass ein Aufrufer einen ungültigen Wert gesendet hat und entsprechend antwortet. Der Dienst kann mit Fehlern Antworten, indem er eine auslöst `RpcException` und den Standard `InvalidArgument` Statuscode verwendet, um das Problem auszudrücken:

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    return base.Get(request, context);
}
```

Nachdem Sie einen geeigneten `Guid` Wert für `traderId` verwendet haben, können Sie das Repository zum Abrufen des Portfolios und zum Zurückgeben des Portfolios an den Client verwenden:

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a>Zuordnen interner Modelle zu GrpC-Nachrichten

Der vorherige Code funktioniert nicht tatsächlich, weil das Repository sein eigenes poco-Modell zurückgibt `Portfolio` , aber GrpC benötigt seine eigene protobuf-Nachricht `Portfolio` . Wenn Sie Daten Übertragungs Typen Entity Framework Typen zuordnen, besteht die beste Lösung darin, eine Konvertierung zwischen beiden zu erstellen. Ein guter Ort zum Einfügen des Codes für diese Konvertierung ist die von protobuf generierte Klasse, die als Klasse deklariert wird, `partial` sodass Sie erweitert werden kann:

```csharp
namespace TraderSys.Portfolios.Protos
{
    public partial class PortfolioItem
    {
        public static PortfolioItem FromRepositoryModel(PortfolioData.Models.PortfolioItem source)
        {
            if (source is null) return null;

            return new PortfolioItem
            {
                Id = source.Id,
                ShareId = source.ShareId,
                Holding = source.Holding,
                CostCents = (int)(source.Cost * 100)
            };
        }
    }

    public partial class Portfolio
    {
        public static Portfolio FromRepositoryModel(PortfolioData.Models.Portfolio source)
        {
            if (source is null) return null;

            var target = new Portfolio
            {
                Id = source.Id,
                TraderId = source.TraderId.ToString(),
            };

            target.Items.AddRange(source.Items.Select(PortfolioItem.FromRepositoryModel));

            return target;
        }
    }
}
```

> [!NOTE]
> Sie können eine Bibliothek wie [AutoMapper](https://automapper.org/) verwenden, um diese Konvertierung von internen Modellklassen in protobuf-Typen zu verarbeiten, solange Sie die Typkonvertierungen auf niedrigerer Ebene wie `string` / `Guid` oder `decimal` / `double` und die Listen Zuordnung konfigurieren.

Nachdem Sie nun über den Konvertierungs Code verfügen, können Sie die Implementierung der- `Get` Methode vervollständigen:

```csharp
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}

```

Die Implementierung der- `GetAll` Methode ist ähnlich. Beachten Sie, dass die `repeated` Felder für protobuf-Nachrichten als `readonly` Eigenschaften vom Typ generiert werden. `RepeatedField<T>` daher müssen Sie diesen Elemente mithilfe der-Methode hinzufügen `AddRange` , wie in diesem Beispiel:

```csharp
public override async Task<GetAllResponse> GetAll(GetAllRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolios = await _repository.GetAllAsync(traderId);

    var response = new GetAllResponse();
    response.Portfolios.AddRange(portfolios.Select(Portfolio.FromRepositoryModel));

    return response;
}
```

Nachdem Sie den WCF-Anforderungs-Antwort-Dienst erfolgreich zu GrpC migriert haben, sehen wir uns an, wie ein Client für ihn aus der Datei erstellt wird `.proto` .

## <a name="generate-client-code"></a>Generieren von Client Code

Erstellen Sie eine .NET Standard-Klassenbibliothek in der gleichen Projekt Mappe, die den-Client enthält. Dies ist in erster Linie ein Beispiel für das Erstellen von Client Code, aber Sie könnten eine solche Bibliothek mithilfe von nuget Verpacken und in einem internen Repository verteilen, damit andere .NET-Teams Sie nutzen können. Fügen Sie der Projekt Mappe eine neue .NET Standard-Klassenbibliothek mit dem Namen hinzu `TraderSys.Portfolios.Client` , und löschen Sie die `Class1.cs` Datei.

> [!CAUTION]
> Das nuget-Paket " [GrpC .net. Client](https://www.nuget.org/packages/Grpc.Net.Client) " erfordert .net Core 3,0 oder höher (oder eine andere .NET Standard 2,1-kompatible Laufzeit). Frühere Versionen von .NET Framework und .net Core werden vom nuget-Paket " [GrpC. Core](https://www.nuget.org/packages/Grpc.Core) " unterstützt.

In Visual Studio 2019 können Sie Verweise auf GrpC-Dienste ähnlich wie in früheren Versionen von Visual Studio zu WCF-Projekten hinzufügen. Dienst Verweise und verbundene Dienste werden jetzt auf der gleichen Benutzeroberfläche verwaltet. Sie können auf die Benutzeroberfläche zugreifen, indem Sie im Projekt in Projektmappen-Explorer mit der rechten Maustaste auf den Knoten **Abhängigkeiten** klicken `TraderSys.Portfolios.Client` und **verbundenen Dienst hinzufügen** auswählen. Wählen Sie im angezeigten Tool Fenster den Abschnitt **Dienst Verweise** aus, und wählen Sie dann **neuen GrpC-Dienst Verweis hinzufügen** aus:

![Verbundene Dienste Benutzeroberfläche in Visual Studio 2019](media/migrate-request-reply/add-connected-service.png)

Navigieren Sie zu der `portfolios.proto` Datei im `TraderSys.Portfolios` Projekt, lassen Sie **Client** unter **Wählen Sie den Typ der zu generierenden Klasse aus**, und wählen Sie dann **OK** aus:

![Dialogfeld "neues GrpC-Dienst Verweis hinzufügen" in Visual Studio 2019](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> Beachten Sie, dass dieses Dialogfeld auch ein URL-Feld enthält. Wenn Ihre Organisation ein Verzeichnis mit Dateien verwaltet, auf `.proto` das zugegriffen werden kann, können Sie Clients erstellen, indem Sie einfach diese URL-Adresse festlegen.

Wenn Sie die Funktion " **verbundenen Dienst hinzufügen** " von Visual Studio verwenden, `portfolios.proto` wird die Datei dem Klassen Bibliotheksprojekt als *verknüpfte Datei* hinzugefügt und nicht als kopiert, sodass Änderungen an der Datei im Dienstprojekt automatisch im Client Projekt angewendet werden. Das- `<Protobuf>` Element in der `csproj` Datei sieht wie folgt aus:

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> Wenn Sie Visual Studio nicht verwenden oder lieber von der Befehlszeile aus arbeiten, können Sie mit dem `dotnet-grpc` globalen Tool protobuf-Verweise in einem .net-GrpC-Projekt verwalten. Weitere Informationen finden Sie in der [ `dotnet-grpc` Dokumentation](/aspnet/core/grpc/dotnet-grpc).

### <a name="use-the-portfolios-service-from-a-client-application"></a>Verwenden des Portfolios-Dienstanbieter aus einer Client Anwendung

Der folgende Code ist ein kurzes Beispiel für die Verwendung des generierten Clients in einer Konsolenanwendung. Eine ausführlichere Untersuchung des GrpC-Client Codes finden Sie am Ende dieses Kapitels.

```csharp
public class Program
{
    public async Task Main(string[] args)
    {
        GetResponse response;

        using (var channel = GrpcChannel.ForAddress("https://localhost:5001"))
        {
            var client = new Protos.Portfolios.PortfoliosClient(channel);

            response = await client.GetAsync(new GetRequest
            {
                TraderId = args[0],
                PortfolioId = int.Parse(args[1])
            });
        }

        foreach (var item in response.Portfolio.Items)
        {
            Console.WriteLine($"Holding {item.Holding} of Share ID {item.ShareId}.");
        }
    }
}
```

Sie haben nun eine einfache WCF-Anwendung zu einem ASP.net Core GrpC-Dienst migriert und einen Client erstellt, um den Dienst aus einer .NET-Anwendung zu nutzen. Im nächsten Abschnitt werden die mehr beteiligten Duplex Dienste behandelt.

>[!div class="step-by-step"]
>[Zurück](create-project.md)
>[Weiter](migrate-duplex-services.md)
