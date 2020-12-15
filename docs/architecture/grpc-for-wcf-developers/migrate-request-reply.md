---
title: Migrieren eines WCF-Anforderungs-/antwortdienstanbieter zu GrpC-GrpC für WCF-Entwickler
description: Erfahren Sie, wie Sie einen einfachen Anforderungs-Antwort-Dienst von WCF zu GrpC migrieren.
ms.date: 09/02/2019
ms.openlocfilehash: 29a7bc77bc3a4becd767fc7a50adff5b746f54bc
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512696"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a><span data-ttu-id="a4237-103">Migrieren eines WCF-Anforderungs-Antwort-Dienstanbieter zu einem unären GrpC-RPC</span><span class="sxs-lookup"><span data-stu-id="a4237-103">Migrate a WCF request-reply service to a gRPC unary RPC</span></span>

<span data-ttu-id="a4237-104">In diesem Abschnitt wird beschrieben, wie ein einfacher Anforderungs-/Antwort-Dienst in WCF zu einem unären RPC-Dienst in ASP.net Core GrpC migriert wird.</span><span class="sxs-lookup"><span data-stu-id="a4237-104">This section covers how to migrate a basic request-reply service in WCF to a unary RPC service in ASP.NET Core gRPC.</span></span> <span data-ttu-id="a4237-105">Diese Dienste sind die einfachsten Dienst Typen sowohl in Windows Communication Foundation (WCF) als auch in GrpC und sind daher ein hervorragender Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="a4237-105">These services are the simplest service types in both Windows Communication Foundation (WCF) and gRPC, so it's an excellent place to start.</span></span> <span data-ttu-id="a4237-106">Nachdem Sie den Dienst migriert haben, erfahren Sie, wie Sie eine Client Bibliothek aus derselben Datei generieren, `.proto` um den Dienst aus einer .NET-Client Anwendung zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="a4237-106">After migrating the service, you'll learn how to generate a client library from the same `.proto` file to consume the service from a .NET client application.</span></span>

## <a name="the-wcf-solution"></a><span data-ttu-id="a4237-107">Die WCF-Lösung</span><span class="sxs-lookup"><span data-stu-id="a4237-107">The WCF solution</span></span>

<span data-ttu-id="a4237-108">Die [Projekt](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) Mappe "Projekt Mappe" umfasst einen einfachen Anforderungs-Antwort-Portfolio Dienst zum Herunterladen eines einzelnen Portfolios oder aller Portfolios für einen bestimmten Händler.</span><span class="sxs-lookup"><span data-stu-id="a4237-108">The [PortfoliosSample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) includes a simple request-reply Portfolio service to download either a single portfolio or all portfolios for a given trader.</span></span> <span data-ttu-id="a4237-109">Der-Dienst wird in der-Schnittstelle `IPortfolioService` mit einem- `ServiceContract` Attribut definiert:</span><span class="sxs-lookup"><span data-stu-id="a4237-109">The service is defined in the interface `IPortfolioService` with a `ServiceContract` attribute:</span></span>

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

<span data-ttu-id="a4237-110">Das `Portfolio` Modell ist eine einfache c#-Klasse, die mit [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) gekennzeichnet ist und eine Liste von- `PortfolioItem` Objekten einschließt.</span><span class="sxs-lookup"><span data-stu-id="a4237-110">The `Portfolio` model is a simple C# class marked with [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) and including a list of `PortfolioItem` objects.</span></span> <span data-ttu-id="a4237-111">Diese Modelle werden im `TraderSys.PortfolioData` Projekt zusammen mit einer Repository-Klasse definiert, die eine Datenzugriffs Abstraktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="a4237-111">These models are defined in the `TraderSys.PortfolioData` project along with a repository class that represents a data access abstraction.</span></span>

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

<span data-ttu-id="a4237-112">Die `ServiceContract` Implementierung verwendet eine Repository-Klasse, die über die Abhängigkeitsinjektion bereitgestellt wird und Instanzen der Typen zurückgibt `DataContract` :</span><span class="sxs-lookup"><span data-stu-id="a4237-112">The `ServiceContract` implementation uses a repository class provided via dependency injection that returns instances of the `DataContract` types:</span></span>

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

## <a name="the-portfoliosproto-file"></a><span data-ttu-id="a4237-113">Die Datei "Portfolios. proto"</span><span class="sxs-lookup"><span data-stu-id="a4237-113">The portfolios.proto file</span></span>

<span data-ttu-id="a4237-114">Wenn Sie die Anweisungen im vorherigen Abschnitt befolgt haben, sollten Sie ein GrpC-Projekt mit einer `portfolios.proto` Datei haben, die wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="a4237-114">If you followed the instructions in the previous section, you should have a gRPC project with a `portfolios.proto` file that looks like this:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

<span data-ttu-id="a4237-115">Der erste Schritt besteht darin, die- `DataContract` Klassen zu ihren protobuf-Entsprechungen zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="a4237-115">The first step is to migrate the `DataContract` classes to their Protobuf equivalents.</span></span>

## <a name="convert-the-datacontract-classes-to-grpc-messages"></a><span data-ttu-id="a4237-116">Konvertieren der DataContract-Klassen in GrpC-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="a4237-116">Convert the DataContract classes to gRPC messages</span></span>

<span data-ttu-id="a4237-117">Die- `PortfolioItem` Klasse wird zuerst in eine protobuf-Nachricht konvertiert, da die- `Portfolio` Klasse von ihr abhängt.</span><span class="sxs-lookup"><span data-stu-id="a4237-117">The `PortfolioItem` class will be converted to a Protobuf message first, because the `Portfolio` class depends on it.</span></span> <span data-ttu-id="a4237-118">Die Klasse ist einfach, und drei der Eigenschaften werden direkt den GrpC-Datentypen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a4237-118">The class is simple, and three of the properties map directly to gRPC data types.</span></span> <span data-ttu-id="a4237-119">Die- `Cost` Eigenschaft, die den für die Freigaben beim Kauf bezahlten Preis darstellt, ist ein `decimal` Feld.</span><span class="sxs-lookup"><span data-stu-id="a4237-119">The `Cost` property, which represents the price paid for the shares at purchase, is a `decimal` field.</span></span> <span data-ttu-id="a4237-120">GrpC unterstützt nur `float` oder `double` für reelle Zahlen, die nicht für Währungen geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="a4237-120">gRPC supports only `float` or `double` for real numbers, which aren't suitable for currency.</span></span> <span data-ttu-id="a4237-121">Da sich die Freigabe Preise um mindestens einen Cent unterscheiden, können die Kosten als `int32` von Cent ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="a4237-121">Because share prices vary by a minimum of one cent, the cost can be expressed as an `int32` of cents.</span></span>

> [!NOTE]
> <span data-ttu-id="a4237-122">Denken Sie daran, `snake_case` für Feldnamen in der Datei zu verwenden `.proto` .</span><span class="sxs-lookup"><span data-stu-id="a4237-122">Remember to use `snake_case` for field names in your `.proto` file.</span></span> <span data-ttu-id="a4237-123">Der c#-Code-Generator konvertiert sie in `PascalCase` für Sie, und Benutzer anderer Sprachen werden Ihnen bei der Einhaltung der verschiedenen Codierungsstandards danken.</span><span class="sxs-lookup"><span data-stu-id="a4237-123">The C# code generator will convert them to `PascalCase` for you, and users of other languages will thank you for respecting their different coding standards.</span></span>

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

<span data-ttu-id="a4237-124">Die `Portfolio` Klasse ist etwas komplizierter.</span><span class="sxs-lookup"><span data-stu-id="a4237-124">The `Portfolio` class is a little more complicated.</span></span> <span data-ttu-id="a4237-125">Im WCF-Code hat der Entwickler einen `Guid` für die `TraderId` -Eigenschaft verwendet und enthält eine `List<PortfolioItem>` .</span><span class="sxs-lookup"><span data-stu-id="a4237-125">In the WCF code, the developer used a `Guid` for the `TraderId` property, and contains a `List<PortfolioItem>`.</span></span> <span data-ttu-id="a4237-126">In protobuf, die keinen erstklassigen `UUID` Typ hat, sollten Sie ein-Element `string` für das `traderId` -Feld verwenden und es in Ihrem eigenen Code analysieren.</span><span class="sxs-lookup"><span data-stu-id="a4237-126">In Protobuf, which doesn't have a first-class `UUID` type, you should use a `string` for the `traderId` field and parse it in your own code.</span></span> <span data-ttu-id="a4237-127">Verwenden Sie für die Liste der Elemente das- `repeated` Schlüsselwort für das Feld.</span><span class="sxs-lookup"><span data-stu-id="a4237-127">For the list of items, use the `repeated` keyword on the field.</span></span>

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

<span data-ttu-id="a4237-128">Nachdem Sie nun über die Daten Meldungen verfügen, können Sie die RPC-Endpunkte für den Dienst deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a4237-128">Now that you have the data messages, you can declare the service RPC endpoints.</span></span>

## <a name="convert-servicecontract-to-a-grpc-service"></a><span data-ttu-id="a4237-129">Konvertieren von ServiceContract in einen GrpC-Dienst</span><span class="sxs-lookup"><span data-stu-id="a4237-129">Convert ServiceContract to a gRPC service</span></span>

<span data-ttu-id="a4237-130">Die WCF `Get` -Methode nimmt zwei Parameter an: `Guid traderId` und `int portfolioId` .</span><span class="sxs-lookup"><span data-stu-id="a4237-130">The WCF `Get` method takes two parameters: `Guid traderId` and `int portfolioId`.</span></span> <span data-ttu-id="a4237-131">GrpC-Dienst Methoden können nur einen einzelnen Parameter verwenden. Daher müssen Sie eine Nachricht erstellen, die die beiden Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="a4237-131">gRPC service methods can take only a single parameter, so you need to create a message to hold the two values.</span></span> <span data-ttu-id="a4237-132">Es ist üblich, diese Anforderungs Objekte mit dem gleichen Namen wie die Methode, gefolgt vom Suffix, zu benennen `Request` .</span><span class="sxs-lookup"><span data-stu-id="a4237-132">It's common practice to name these request objects with the same name as the method followed by the suffix `Request`.</span></span> <span data-ttu-id="a4237-133">Auch hier `string` wird für das `traderId` Feld anstelle von verwendet `Guid` .</span><span class="sxs-lookup"><span data-stu-id="a4237-133">Again, `string` is being used for the `traderId` field instead of `Guid`.</span></span>

<span data-ttu-id="a4237-134">Der Dienst könnte eine `Portfolio` Nachricht direkt zurückgeben, aber dies kann sich in Zukunft auf die Abwärtskompatibilität auswirken.</span><span class="sxs-lookup"><span data-stu-id="a4237-134">The service could just return a `Portfolio` message directly, but again, this could affect backward compatibility in the future.</span></span> <span data-ttu-id="a4237-135">Es empfiehlt sich `Request` , separate und `Response` Nachrichten für jede Methode in einem Dienst zu definieren, auch wenn viele von Ihnen momentan gleich sind.</span><span class="sxs-lookup"><span data-stu-id="a4237-135">It's a good practice to define separate `Request` and `Response` messages for every method in a service, even if many of them are the same right now.</span></span> <span data-ttu-id="a4237-136">Deklarieren Sie also eine `GetResponse` Nachricht mit einem einzelnen `Portfolio` Feld.</span><span class="sxs-lookup"><span data-stu-id="a4237-136">So declare a `GetResponse` message with a single `Portfolio` field.</span></span>

<span data-ttu-id="a4237-137">Dieses Beispiel zeigt die Deklaration der GrpC-Dienst Methode mit der folgenden `GetRequest` Meldung:</span><span class="sxs-lookup"><span data-stu-id="a4237-137">This example shows the declaration of the gRPC service method with the `GetRequest` message:</span></span>

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

<span data-ttu-id="a4237-138">Die WCF- `GetAll` Methode benötigt nur einen einzigen Parameter, `traderId` , daher kann es vorkommen, dass Sie `string` als Parametertyp angeben könnten.</span><span class="sxs-lookup"><span data-stu-id="a4237-138">The WCF `GetAll` method takes only a single parameter, `traderId`, so it might seem that you could specify `string` as the parameter type.</span></span> <span data-ttu-id="a4237-139">GrpC erfordert jedoch einen definierten Nachrichtentyp.</span><span class="sxs-lookup"><span data-stu-id="a4237-139">But gRPC requires a defined message type.</span></span> <span data-ttu-id="a4237-140">Durch diese Anforderung wird die Verwendung von benutzerdefinierten Nachrichten für alle Eingaben und Ausgaben für zukünftige Abwärtskompatibilität erzwungen.</span><span class="sxs-lookup"><span data-stu-id="a4237-140">This requirement helps to enforce the practice of using custom messages for all inputs and outputs, for future backward compatibility.</span></span>

<span data-ttu-id="a4237-141">Die WCF-Methode gibt auch zurück `List<Portfolio>` , aber aus demselben Grund lässt Sie einfache Parametertypen nicht zu, da GrpC nicht `repeated Portfolio` als Rückgabetyp zulässt.</span><span class="sxs-lookup"><span data-stu-id="a4237-141">The WCF method also returns a `List<Portfolio>`, but for the same reason it doesn't allow simple parameter types, gRPC won't allow `repeated Portfolio` as a return type.</span></span> <span data-ttu-id="a4237-142">Erstellen Sie stattdessen einen `GetAllResponse` Typ, um die Liste zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a4237-142">Instead, create a `GetAllResponse` type to wrap the list.</span></span>

> [!WARNING]
> <span data-ttu-id="a4237-143">Möglicherweise sind Sie verlockend, eine `PortfolioList` Nachricht zu erstellen und Sie in mehreren Dienst Methoden zu verwenden, aber Sie sollten dieser Versuchung widerstehen.</span><span class="sxs-lookup"><span data-stu-id="a4237-143">You might be tempted to create a `PortfolioList` message or something similar and use it across multiple service methods, but you should resist this temptation.</span></span> <span data-ttu-id="a4237-144">Es ist nicht möglich, zu wissen, wie sich die verschiedenen Methoden in einem Dienst weiterentwickeln, sodass die Nachrichten spezifisch und ordnungsgemäß getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="a4237-144">It's impossible to know how the various methods on a service will evolve, so keep their messages specific and cleanly separated.</span></span>

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

<span data-ttu-id="a4237-145">Wenn Sie Ihr Projekt mit diesen Änderungen speichern, wird das GrpC-Buildziel im Hintergrund ausgeführt und generiert alle protobuf-Nachrichten Typen und eine Basisklasse, die Sie erben können, um den Dienst zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a4237-145">If you save your project with these changes, the gRPC build target will run in the background and generate all the Protobuf message types and a base class that you can inherit to implement the service.</span></span>

<span data-ttu-id="a4237-146">Öffnen Sie die `Services/GreeterService.cs` -Klasse, und löschen Sie den Beispielcode.</span><span class="sxs-lookup"><span data-stu-id="a4237-146">Open the `Services/GreeterService.cs` class and delete the example code.</span></span> <span data-ttu-id="a4237-147">Nun können Sie die Portfolio Service-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a4237-147">Now you can add the Portfolio service implementation.</span></span> <span data-ttu-id="a4237-148">Die generierte Basisklasse befindet sich im `Protos` -Namespace und wird als eine schsted-Klasse generiert.</span><span class="sxs-lookup"><span data-stu-id="a4237-148">The generated base class will be in the `Protos` namespace and is generated as a nested class.</span></span> <span data-ttu-id="a4237-149">GrpC erstellt eine statische Klasse mit dem gleichen Namen wie der Dienst in der `.proto` Datei und eine Basisklasse mit dem Suffix `Base` innerhalb dieser statischen Klasse, sodass der vollständige Bezeichner für den Basistyp ist `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase` .</span><span class="sxs-lookup"><span data-stu-id="a4237-149">gRPC creates a static class with the same name as the service in the `.proto` file and a base class with the suffix `Base` inside that static class, so the full identifier for the base type is `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span></span>

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

<span data-ttu-id="a4237-150">Die-Basisklasse deklariert `virtual` Methoden für `Get` und `GetAll` , die überschrieben werden können, um den-Dienst zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a4237-150">The base class declares `virtual` methods for `Get` and `GetAll` that can be overridden to implement the service.</span></span> <span data-ttu-id="a4237-151">Die Methoden sind `virtual` nicht `abstract` so, dass der Dienst einen expliziten GrpC-Statuscode zurückgeben kann, wenn Sie ihn nicht implementieren, `Unimplemented` ähnlich wie `NotImplementedException` bei einem regulären c#-Code.</span><span class="sxs-lookup"><span data-stu-id="a4237-151">The methods are `virtual` rather than `abstract` so that if you don't implement them, the service can return an explicit gRPC `Unimplemented` status code, much like you might throw a `NotImplementedException` in regular C# code.</span></span>

<span data-ttu-id="a4237-152">Die Signatur für alle unären GrpC-Dienst Methoden in ASP.net Core ist konsistent.</span><span class="sxs-lookup"><span data-stu-id="a4237-152">The signature for all gRPC unary service methods in ASP.NET Core is consistent.</span></span> <span data-ttu-id="a4237-153">Es gibt zwei Parameter: der erste ist der Nachrichtentyp, der in der Datei deklariert ist `.proto` , und der zweite ist eine `ServerCallContext` , die ähnlich wie die `HttpContext` von ASP.net Core funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a4237-153">There are two parameters: the first is the message type declared in the `.proto` file, and the second is a `ServerCallContext` that works similarly to the `HttpContext` from ASP.NET Core.</span></span> <span data-ttu-id="a4237-154">Tatsächlich gibt es eine Erweiterungsmethode, `GetHttpContext` die für die- `ServerCallContext` Klasse aufgerufen wird, die Sie verwenden können, um den zugrunde liegenden zu erhalten `HttpContext` , obwohl Sie Sie nicht häufig verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="a4237-154">In fact, there's an extension method called `GetHttpContext` on the `ServerCallContext` class that you can use to get the underlying `HttpContext`, although you shouldn't need to use it often.</span></span> <span data-ttu-id="a4237-155">Wir werden uns `ServerCallContext` später in diesem Kapitel und auch im Kapitel, in dem die Authentifizierung erläutert wird, ansehen.</span><span class="sxs-lookup"><span data-stu-id="a4237-155">We'll take a look at `ServerCallContext` later in this chapter, and also in the chapter that discusses authentication.</span></span>

<span data-ttu-id="a4237-156">Der Rückgabetyp der Methode ist ein `Task<T>` , wobei `T` der Antwort Nachrichtentyp ist.</span><span class="sxs-lookup"><span data-stu-id="a4237-156">The method's return type is a `Task<T>`, where `T` is the response message type.</span></span> <span data-ttu-id="a4237-157">Alle GrpC-Dienst Methoden sind asynchron.</span><span class="sxs-lookup"><span data-stu-id="a4237-157">All gRPC service methods are asynchronous.</span></span>

## <a name="migrate-the-portfoliodata-library-to-net-core"></a><span data-ttu-id="a4237-158">Migrieren der videodata-Bibliothek zu .net Core</span><span class="sxs-lookup"><span data-stu-id="a4237-158">Migrate the PortfolioData library to .NET Core</span></span>

<span data-ttu-id="a4237-159">An diesem Punkt benötigt das Projekt das Portfolio-Repository und die Modelle, die in der `TraderSys.PortfolioData` Klassenbibliothek in der WCF-Lösung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a4237-159">At this point, the project needs the Portfolio repository and models contained in the `TraderSys.PortfolioData` class library in the WCF solution.</span></span> <span data-ttu-id="a4237-160">Die einfachste Möglichkeit, Sie zu übernehmen, besteht darin, eine neue Klassenbibliothek zu erstellen, indem Sie entweder das Visual Studio-Dialogfeld " **Neues Projekt** " mit der Vorlage für die Klassenbibliothek (.NET Standard) verwenden, oder über die Befehlszeile in der Befehlszeile, indem Sie .net Core-CLI die folgenden Befehle aus dem Verzeichnis ausführen, das die `TraderSys.sln` Datei enthält:</span><span class="sxs-lookup"><span data-stu-id="a4237-160">The easiest way to bring them across is to create a new class library by using either the Visual Studio **New project** dialog box with the Class Library (.NET Standard) template, or from the command line by using the .NET Core CLI, running these commands from the directory that contains the `TraderSys.sln` file:</span></span>

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

<span data-ttu-id="a4237-161">Nachdem Sie die Bibliothek erstellt und der Projekt Mappe hinzugefügt haben, löschen Sie die generierte `Class1.cs` Datei, und kopieren Sie die Dateien aus der Bibliothek der WCF-Projekt Mappe in den Ordner der neuen Klassenbibliothek, wobei die Ordnerstruktur beibehalten wird:</span><span class="sxs-lookup"><span data-stu-id="a4237-161">After you've created the library and added it to the solution, delete the generated `Class1.cs` file and copy the files from the WCF solution's library into the new class library's folder, keeping the folder structure:</span></span>

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

<span data-ttu-id="a4237-162">.Net-Projekte im SDK-Stil enthalten automatisch alle `.cs` Dateien in oder in Ihrem eigenen Verzeichnis, sodass Sie Sie nicht explizit dem Projekt hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="a4237-162">SDK-style .NET projects automatically include any `.cs` files in or under their own directory, so you don't need to explicitly add them to the project.</span></span> <span data-ttu-id="a4237-163">Der einzige Schritt besteht darin, das `DataContract` -Attribut und das- `DataMember` Attribut aus den Klassen und zu entfernen, `Portfolio` `PortfolioItem` sodass Sie einfache c#-Klassen sind:</span><span class="sxs-lookup"><span data-stu-id="a4237-163">The only step remaining is to remove the `DataContract` and `DataMember` attributes from the `Portfolio` and `PortfolioItem` classes so they're plain old C# classes:</span></span>

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

## <a name="use-aspnet-core-dependency-injection"></a><span data-ttu-id="a4237-164">Verwenden von ASP.net Core-Abhängigkeitsinjektion</span><span class="sxs-lookup"><span data-stu-id="a4237-164">Use ASP.NET Core dependency injection</span></span>

<span data-ttu-id="a4237-165">Nun können Sie dem GrpC-Anwendungsprojekt einen Verweis auf diese Bibliothek hinzufügen und die `PortfolioRepository` Klasse mithilfe der Abhängigkeitsinjektion in der GrpC-Dienst Implementierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4237-165">Now you can add a reference to this library to the gRPC application project and consume the `PortfolioRepository` class by using dependency injection in the gRPC service implementation.</span></span> <span data-ttu-id="a4237-166">In der WCF-Anwendung wurde die Abhängigkeitsinjektion vom autofac IOC-Container bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a4237-166">In the WCF application, dependency injection was provided by the Autofac IoC container.</span></span> <span data-ttu-id="a4237-167">Die Abhängigkeitsinjektion ASP.net Core wurde in integriert.</span><span class="sxs-lookup"><span data-stu-id="a4237-167">ASP.NET Core has dependency injection baked in.</span></span> <span data-ttu-id="a4237-168">Sie können das Repository in der- `ConfigureServices` Methode in der- `Startup` Klasse registrieren:</span><span class="sxs-lookup"><span data-stu-id="a4237-168">You can register the repository in the `ConfigureServices` method in the `Startup` class:</span></span>

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

<span data-ttu-id="a4237-169">Die- `IPortfolioRepository` Implementierung kann nun wie folgt als Konstruktorparameter in der-Klasse angegeben werden `PortfolioService` :</span><span class="sxs-lookup"><span data-stu-id="a4237-169">The `IPortfolioRepository` implementation can now be specified as a constructor parameter in the `PortfolioService` class, as follows:</span></span>

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

## <a name="implement-the-grpc-service"></a><span data-ttu-id="a4237-170">Implementieren des GrpC-Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="a4237-170">Implement the gRPC service</span></span>

<span data-ttu-id="a4237-171">Nachdem Sie die Nachrichten und den Dienst in der Datei deklariert haben `portfolios.proto` , müssen Sie die Dienst Methoden in der Klasse implementieren, `PortfolioService` die von der vom GrpC generierten Klasse erbt `Portfolios.PortfoliosBase` .</span><span class="sxs-lookup"><span data-stu-id="a4237-171">Now that you've declared your messages and your service in the `portfolios.proto` file, you have to implement the service methods in the `PortfolioService` class that inherits from the gRPC-generated `Portfolios.PortfoliosBase` class.</span></span> <span data-ttu-id="a4237-172">Die-Methoden werden als `virtual` in der-Basisklasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="a4237-172">The methods are declared as `virtual` in the base class.</span></span> <span data-ttu-id="a4237-173">Wenn Sie Sie nicht überschreiben, geben Sie standardmäßig den Statuscode "nicht implementiert" von GrpC zurück.</span><span class="sxs-lookup"><span data-stu-id="a4237-173">If you don't override them, they'll return a gRPC "Not Implemented" status code by default.</span></span>

<span data-ttu-id="a4237-174">Beginnen Sie mit der Implementierung der- `Get` Methode.</span><span class="sxs-lookup"><span data-stu-id="a4237-174">Start by implementing the `Get` method.</span></span> <span data-ttu-id="a4237-175">Die Standard Überschreibung sieht wie in diesem Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="a4237-175">The default override looks like this example:</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

<span data-ttu-id="a4237-176">Das erste Problem ist, dass `request.TraderId` eine Zeichenfolge ist und der Dienst eine erfordert `Guid` .</span><span class="sxs-lookup"><span data-stu-id="a4237-176">The first problem is that `request.TraderId` is a string, and the service requires a `Guid`.</span></span> <span data-ttu-id="a4237-177">Obwohl das erwartete Format für die Zeichenfolge ist `UUID` , muss der Code die Möglichkeit behandeln, dass ein Aufrufer einen ungültigen Wert gesendet hat und entsprechend antwortet.</span><span class="sxs-lookup"><span data-stu-id="a4237-177">Even though the expected format for the string is `UUID`, the code has to deal with the possibility that a caller has sent an invalid value and respond appropriately.</span></span> <span data-ttu-id="a4237-178">Der Dienst kann mit Fehlern Antworten, indem er eine auslöst `RpcException` und den Standard `InvalidArgument` Statuscode verwendet, um das Problem auszudrücken:</span><span class="sxs-lookup"><span data-stu-id="a4237-178">The service can respond with errors by throwing an `RpcException` and use the standard `InvalidArgument` status code to express the problem:</span></span>

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

<span data-ttu-id="a4237-179">Nachdem Sie einen geeigneten `Guid` Wert für `traderId` verwendet haben, können Sie das Repository zum Abrufen des Portfolios und zum Zurückgeben des Portfolios an den Client verwenden:</span><span class="sxs-lookup"><span data-stu-id="a4237-179">After there's a proper `Guid` value for `traderId`, you can use the repository to retrieve the Portfolio and return it to the client:</span></span>

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a><span data-ttu-id="a4237-180">Zuordnen interner Modelle zu GrpC-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="a4237-180">Map internal models to gRPC messages</span></span>

<span data-ttu-id="a4237-181">Der vorherige Code funktioniert nicht tatsächlich, weil das Repository sein eigenes poco-Modell zurückgibt `Portfolio` , aber GrpC benötigt seine eigene protobuf-Nachricht `Portfolio` .</span><span class="sxs-lookup"><span data-stu-id="a4237-181">The previous code doesn't actually work because the repository is returning its own POCO model `Portfolio`, but gRPC needs its own Protobuf message `Portfolio`.</span></span> <span data-ttu-id="a4237-182">Wenn Sie Daten Übertragungs Typen Entity Framework Typen zuordnen, besteht die beste Lösung darin, eine Konvertierung zwischen beiden zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4237-182">As when you map Entity Framework types to data transfer types, the best solution is to provide a conversion between the two.</span></span> <span data-ttu-id="a4237-183">Ein guter Ort zum Einfügen des Codes für diese Konvertierung ist die von protobuf generierte Klasse, die als Klasse deklariert wird, `partial` sodass Sie erweitert werden kann:</span><span class="sxs-lookup"><span data-stu-id="a4237-183">A good place to put the code for this conversion is in the Protobuf-generated class, which is declared as a `partial` class so it can be extended:</span></span>

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
> <span data-ttu-id="a4237-184">Sie können eine Bibliothek wie [AutoMapper](https://automapper.org/) verwenden, um diese Konvertierung von internen Modellklassen in protobuf-Typen zu verarbeiten, solange Sie die Typkonvertierungen auf niedrigerer Ebene wie `string` / `Guid` oder `decimal` / `double` und die Listen Zuordnung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a4237-184">You could use a library like [AutoMapper](https://automapper.org/) to handle this conversion from internal model classes to Protobuf types, as long as you configure the lower-level type conversions like `string`/`Guid` or `decimal`/`double` and the list mapping.</span></span>

<span data-ttu-id="a4237-185">Nachdem Sie nun über den Konvertierungs Code verfügen, können Sie die Implementierung der- `Get` Methode vervollständigen:</span><span class="sxs-lookup"><span data-stu-id="a4237-185">Now that you have the conversion code in place, you can complete the `Get` method implementation:</span></span>

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

<span data-ttu-id="a4237-186">Die Implementierung der- `GetAll` Methode ist ähnlich.</span><span class="sxs-lookup"><span data-stu-id="a4237-186">The implementation of the `GetAll` method is similar.</span></span> <span data-ttu-id="a4237-187">Beachten Sie, dass die `repeated` Felder für protobuf-Nachrichten als `readonly` Eigenschaften vom Typ generiert werden. `RepeatedField<T>` daher müssen Sie diesen Elemente mithilfe der-Methode hinzufügen `AddRange` , wie in diesem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a4237-187">Note that the `repeated` fields on Protobuf messages are generated as `readonly` properties of type `RepeatedField<T>`, so you have to add items to them by using the `AddRange` method, like in this example:</span></span>

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

<span data-ttu-id="a4237-188">Nachdem Sie den WCF-Anforderungs-Antwort-Dienst erfolgreich zu GrpC migriert haben, sehen wir uns an, wie ein Client für ihn aus der Datei erstellt wird `.proto` .</span><span class="sxs-lookup"><span data-stu-id="a4237-188">Having successfully migrated the WCF request-reply service to gRPC, let's look at creating a client for it from the `.proto` file.</span></span>

## <a name="generate-client-code"></a><span data-ttu-id="a4237-189">Generieren von Client Code</span><span class="sxs-lookup"><span data-stu-id="a4237-189">Generate client code</span></span>

<span data-ttu-id="a4237-190">Erstellen Sie eine .NET Standard-Klassenbibliothek in der gleichen Projekt Mappe, die den-Client enthält.</span><span class="sxs-lookup"><span data-stu-id="a4237-190">Create a .NET Standard class library in the same solution to contain the client.</span></span> <span data-ttu-id="a4237-191">Dies ist in erster Linie ein Beispiel für das Erstellen von Client Code, aber Sie könnten eine solche Bibliothek mithilfe von nuget Verpacken und in einem internen Repository verteilen, damit andere .NET-Teams Sie nutzen können.</span><span class="sxs-lookup"><span data-stu-id="a4237-191">This is primarily an example of creating client code, but you could package such a library by using NuGet and distribute it on an internal repository for other .NET teams to consume.</span></span> <span data-ttu-id="a4237-192">Fügen Sie der Projekt Mappe eine neue .NET Standard-Klassenbibliothek mit dem Namen hinzu `TraderSys.Portfolios.Client` , und löschen Sie die `Class1.cs` Datei.</span><span class="sxs-lookup"><span data-stu-id="a4237-192">Go ahead and add a new .NET Standard class library called `TraderSys.Portfolios.Client` to the solution and delete the `Class1.cs` file.</span></span>

> [!CAUTION]
> <span data-ttu-id="a4237-193">Das nuget-Paket " [GrpC .net. Client](https://www.nuget.org/packages/Grpc.Net.Client) " erfordert .net Core 3,0 (oder eine andere .NET Standard 2,1-kompatible Laufzeit).</span><span class="sxs-lookup"><span data-stu-id="a4237-193">The [Grpc.Net.Client](https://www.nuget.org/packages/Grpc.Net.Client) NuGet package requires .NET Core 3.0 (or another .NET Standard 2.1-compliant runtime).</span></span> <span data-ttu-id="a4237-194">Frühere Versionen von .NET Framework und .net Core werden vom nuget-Paket " [GrpC. Core](https://www.nuget.org/packages/Grpc.Core) " unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4237-194">Earlier versions of .NET Framework and .NET Core are supported by the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core) NuGet package.</span></span>

<span data-ttu-id="a4237-195">In Visual Studio 2019 können Sie Verweise auf GrpC-Dienste ähnlich wie in früheren Versionen von Visual Studio zu WCF-Projekten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a4237-195">In Visual Studio 2019, you can add references to gRPC services in a way that's similar to how you'd add service references to WCF projects in earlier versions of Visual Studio.</span></span> <span data-ttu-id="a4237-196">Dienst Verweise und verbundene Dienste werden jetzt auf der gleichen Benutzeroberfläche verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a4237-196">Service references and connected services are all managed under the same UI now.</span></span> <span data-ttu-id="a4237-197">Sie können auf die Benutzeroberfläche zugreifen, indem Sie im Projekt in Projektmappen-Explorer mit der rechten Maustaste auf den Knoten **Abhängigkeiten** klicken `TraderSys.Portfolios.Client` und **verbundenen Dienst hinzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="a4237-197">You can access the UI by right-clicking the **Dependencies** node in the `TraderSys.Portfolios.Client` project in Solution Explorer and selecting **Add Connected Service**.</span></span> <span data-ttu-id="a4237-198">Wählen Sie im angezeigten Tool Fenster den Abschnitt **Dienst Verweise** aus, und wählen Sie dann **neuen GrpC-Dienst Verweis hinzufügen** aus:</span><span class="sxs-lookup"><span data-stu-id="a4237-198">In the tool window that appears, select the **Service References** section and then select **Add new gRPC service reference**:</span></span>

![Verbundene Dienste Benutzeroberfläche in Visual Studio 2019](media/migrate-request-reply/add-connected-service.png)

<span data-ttu-id="a4237-200">Navigieren Sie zu der `portfolios.proto` Datei im `TraderSys.Portfolios` Projekt, lassen Sie **Client** unter **Wählen Sie den Typ der zu generierenden Klasse aus**, und wählen Sie dann **OK** aus:</span><span class="sxs-lookup"><span data-stu-id="a4237-200">Browse to the `portfolios.proto` file in the `TraderSys.Portfolios` project, leave **Client** under **Select the type of class to be generated**, and then select **OK**:</span></span>

![Dialogfeld "neues GrpC-Dienst Verweis hinzufügen" in Visual Studio 2019](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> <span data-ttu-id="a4237-202">Beachten Sie, dass dieses Dialogfeld auch ein URL-Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="a4237-202">Notice that this dialog box also provides a URL field.</span></span> <span data-ttu-id="a4237-203">Wenn Ihre Organisation ein Verzeichnis mit Dateien verwaltet, auf `.proto` das zugegriffen werden kann, können Sie Clients erstellen, indem Sie einfach diese URL-Adresse festlegen.</span><span class="sxs-lookup"><span data-stu-id="a4237-203">If your organization maintains a web-accessible directory of `.proto` files, you can create clients just by setting this URL address.</span></span>

<span data-ttu-id="a4237-204">Wenn Sie die Funktion " **verbundenen Dienst hinzufügen** " von Visual Studio verwenden, `portfolios.proto` wird die Datei dem Klassen Bibliotheksprojekt als *verknüpfte Datei* hinzugefügt und nicht als kopiert, sodass Änderungen an der Datei im Dienstprojekt automatisch im Client Projekt angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4237-204">When you use the Visual Studio **Add Connected Service** feature, the `portfolios.proto` file is added to the class library project as a *linked file* rather than copied, so changes to the file in the service project will automatically be applied in the client project.</span></span> <span data-ttu-id="a4237-205">Das- `<Protobuf>` Element in der `csproj` Datei sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="a4237-205">The `<Protobuf>` element in the `csproj` file looks like this:</span></span>

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> <span data-ttu-id="a4237-206">Wenn Sie Visual Studio nicht verwenden oder lieber von der Befehlszeile aus arbeiten, können Sie mit dem `dotnet-grpc` globalen Tool protobuf-Verweise in einem .net-GrpC-Projekt verwalten.</span><span class="sxs-lookup"><span data-stu-id="a4237-206">If you're not using Visual Studio or prefer to work from the command line, you can use the `dotnet-grpc` global tool to manage Protobuf references in a .NET gRPC project.</span></span> <span data-ttu-id="a4237-207">Weitere Informationen finden Sie in der [ `dotnet-grpc` Dokumentation](/aspnet/core/grpc/dotnet-grpc).</span><span class="sxs-lookup"><span data-stu-id="a4237-207">For more information, see the [`dotnet-grpc` documentation](/aspnet/core/grpc/dotnet-grpc).</span></span>

### <a name="use-the-portfolios-service-from-a-client-application"></a><span data-ttu-id="a4237-208">Verwenden des Portfolios-Dienstanbieter aus einer Client Anwendung</span><span class="sxs-lookup"><span data-stu-id="a4237-208">Use the Portfolios service from a client application</span></span>

<span data-ttu-id="a4237-209">Der folgende Code ist ein kurzes Beispiel für die Verwendung des generierten Clients in einer Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="a4237-209">The following code is a brief example of how to use the generated client in a console application.</span></span> <span data-ttu-id="a4237-210">Eine ausführlichere Untersuchung des GrpC-Client Codes finden Sie am Ende dieses Kapitels.</span><span class="sxs-lookup"><span data-stu-id="a4237-210">A more detailed exploration of the gRPC client code is at the end of this chapter.</span></span>

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

<span data-ttu-id="a4237-211">Sie haben nun eine einfache WCF-Anwendung zu einem ASP.net Core GrpC-Dienst migriert und einen Client erstellt, um den Dienst aus einer .NET-Anwendung zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="a4237-211">You've now migrated a basic WCF application to an ASP.NET Core gRPC service and created a client to consume the service from a .NET application.</span></span> <span data-ttu-id="a4237-212">Im nächsten Abschnitt werden die mehr beteiligten Duplex Dienste behandelt.</span><span class="sxs-lookup"><span data-stu-id="a4237-212">The next section will cover the more involved duplex services.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a4237-213">[Zurück](create-project.md)
>[Weiter](migrate-duplex-services.md)</span><span class="sxs-lookup"><span data-stu-id="a4237-213">[Previous](create-project.md)
[Next](migrate-duplex-services.md)</span></span>
