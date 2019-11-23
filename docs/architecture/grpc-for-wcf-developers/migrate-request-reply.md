---
title: Migrieren eines WCF-Anforderungs-/antwortdienstanbieter zu GrpC-GrpC für WCF-Entwickler
description: Erfahren Sie, wie Sie einen einfachen Anforderungs-Antwort-Dienst von WCF zu GrpC migrieren.
ms.date: 09/02/2019
ms.openlocfilehash: f0b20e7b374438f90d83aebc6035a4e4dd94ae18
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971786"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a><span data-ttu-id="f2dbd-103">Migrieren eines WCF-Anforderungs-Antwort-Dienstanbieter zu einem unären GrpC-RPC</span><span class="sxs-lookup"><span data-stu-id="f2dbd-103">Migrate a WCF request-reply service to a gRPC unary RPC</span></span>

<span data-ttu-id="f2dbd-104">In diesem Abschnitt wird beschrieben, wie ein einfacher Anforderungs-/Antwort-Dienst in WCF zu einem unären RPC-Dienst in ASP.net Core GrpC migriert wird.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-104">This section covers how to migrate a basic request-reply service in WCF to a unary RPC service in ASP.NET Core gRPC.</span></span> <span data-ttu-id="f2dbd-105">Diese Dienste sind die einfachsten Dienst Typen sowohl in Windows Communication Foundation (WCF) als auch in GrpC und sind daher ein hervorragender Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-105">These services are the simplest service types in both Windows Communication Foundation (WCF) and gRPC, so it's an excellent place to start.</span></span> <span data-ttu-id="f2dbd-106">Nachdem Sie den Dienst migriert haben, erfahren Sie, wie Sie eine Client Bibliothek aus derselben `.proto` Datei generieren, um den Dienst aus einer .NET-Client Anwendung zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-106">After migrating the service, you'll learn how to generate a client library from the same `.proto` file to consume the service from a .NET client application.</span></span>

## <a name="the-wcf-solution"></a><span data-ttu-id="f2dbd-107">Die WCF-Lösung</span><span class="sxs-lookup"><span data-stu-id="f2dbd-107">The WCF solution</span></span>

<span data-ttu-id="f2dbd-108">Die [Projekt](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) Mappe "Projekt Mappe" umfasst einen einfachen Anforderungs-Antwort-Portfolio Dienst zum Herunterladen eines einzelnen Portfolios oder aller Portfolios für einen bestimmten Händler.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-108">The [PortfoliosSample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) includes a simple Request-Reply Portfolio service to download a single portfolio, or all portfolios for a given Trader.</span></span> <span data-ttu-id="f2dbd-109">Der-Dienst wird in der-Schnittstelle definiert, `IPortfolioService` mit einem `ServiceContract`-Attribut:</span><span class="sxs-lookup"><span data-stu-id="f2dbd-109">The service is defined in the interface `IPortfolioService` with a `ServiceContract` attribute:</span></span>

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

<span data-ttu-id="f2dbd-110">Das `Portfolio` Modell ist eine einfache C# , mit [DataContract](xref:System.Runtime.Serialization.DataContractAttribute)markierte Klasse, einschließlich einer Liste von `PortfolioItem` Objekten.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-110">The `Portfolio` model is a simple C# class marked with [DataContract](xref:System.Runtime.Serialization.DataContractAttribute), including a list of `PortfolioItem` objects.</span></span> <span data-ttu-id="f2dbd-111">Diese Modelle werden im `TraderSys.PortfolioData`-Projekt zusammen mit einer Repository-Klasse definiert, die eine Datenzugriffs Abstraktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-111">These models are defined in the `TraderSys.PortfolioData` project, along with a repository class representing a data access abstraction.</span></span>

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

<span data-ttu-id="f2dbd-112">Die `ServiceContract`-Implementierung verwendet eine von der Abhängigkeitsinjektion bereitgestellte Repository-Klasse, die Instanzen der `DataContract` Typen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-112">The `ServiceContract` implementation uses a repository class provided via dependency injection that returns instances of the `DataContract` types.</span></span>

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

## <a name="the-portfoliosproto-file"></a><span data-ttu-id="f2dbd-113">Die Datei "Portfolios. proto"</span><span class="sxs-lookup"><span data-stu-id="f2dbd-113">The portfolios.proto file</span></span>

<span data-ttu-id="f2dbd-114">Wenn Sie die Anweisungen im vorherigen Abschnitt befolgt haben, sollten Sie ein GrpC-Projekt mit einer `portfolios.proto`-Datei haben, die wie folgt aussieht.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-114">If you followed the instructions in the previous section, you should have a gRPC project with a `portfolios.proto` file that looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

<span data-ttu-id="f2dbd-115">Der erste Schritt besteht darin, die `DataContract` Klassen zu ihren protobuf-Entsprechungen zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-115">The first step is to migrate the `DataContract` classes to their Protobuf equivalents.</span></span>

## <a name="convert-the-datacontracts-to-grpc-messages"></a><span data-ttu-id="f2dbd-116">DataContracts in GrpC-Nachrichten konvertieren</span><span class="sxs-lookup"><span data-stu-id="f2dbd-116">Convert the DataContracts to gRPC messages</span></span>

<span data-ttu-id="f2dbd-117">Die `PortfolioItem`-Klasse wird zuerst in eine protobuf-Nachricht konvertiert, da die `Portfolio`-Klasse davon abhängt.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-117">The `PortfolioItem` class will be converted to a Protobuf message first, as the `Portfolio` class depends on it.</span></span> <span data-ttu-id="f2dbd-118">Die-Klasse ist sehr einfach, und drei der Eigenschaften werden direkt den GrpC-Datentypen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-118">The class is very simple, and three of the properties map directly to gRPC data types.</span></span> <span data-ttu-id="f2dbd-119">Die `Cost`-Eigenschaft, die den für die Freigaben kostenpflichtigen Preis darstellt, ist ein `decimal` Feld, und GrpC unterstützt nur `float` oder `double` für reelle Zahlen, die nicht für Währungen geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-119">The `Cost` property, representing the price paid for the shares at purchase, is a `decimal` field, and gRPC only supports `float` or `double` for real numbers, which aren't suitable for currency.</span></span> <span data-ttu-id="f2dbd-120">Da sich die Freigabe Preise um mindestens einen Cent unterscheiden, können die Kosten als `int32` von Cent ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-120">Since share prices vary by a minimum of one cent, the cost can be expressed as an `int32` of cents.</span></span>

> [!NOTE]
> <span data-ttu-id="f2dbd-121">Denken Sie daran, `camelCase` für Feldnamen in ihrer `.proto` Datei zu verwenden. der C# Code-Generator konvertiert sie für Sie in `PascalCase`, und Benutzer anderer Sprachen werden Ihnen bei der Einhaltung der verschiedenen Codierungsstandards danken.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-121">Remember to use `camelCase` for field names in your `.proto` file; the C# code generator will convert them to `PascalCase` for you, and users of other languages will thank you for respecting their different coding standards.</span></span>

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

<span data-ttu-id="f2dbd-122">Die `Portfolio`-Klasse ist etwas komplizierter.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-122">The `Portfolio` class is a little more complicated.</span></span> <span data-ttu-id="f2dbd-123">Im WCF-Code hat der Entwickler eine `Guid` für die `TraderId`-Eigenschaft verwendet und enthält eine `List<PortfolioItem>`.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-123">In the WCF code, the developer used a `Guid` for the `TraderId` property, and contains a `List<PortfolioItem>`.</span></span> <span data-ttu-id="f2dbd-124">In protobuf, die keinen erstklassigen `UUID` Typ hat, sollten Sie eine `string` für das `traderId` Feld verwenden und Sie in Ihrem eigenen Code analysieren.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-124">In Protobuf, which doesn't have a first-class `UUID` type, you should use a `string` for the `traderId` field and parse it in your own code.</span></span> <span data-ttu-id="f2dbd-125">Verwenden Sie für die Liste der Elemente das `repeated`-Schlüsselwort für das Feld.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-125">For the list of items, use the `repeated` keyword on the field.</span></span>

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

<span data-ttu-id="f2dbd-126">Nun haben wir unsere Daten Meldungen, wir können die RPC-Endpunkte für den Dienst deklarieren.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-126">Now we have our data messages, we can declare the service RPC endpoints.</span></span>

## <a name="convert-the-servicecontract-to-a-grpc-service"></a><span data-ttu-id="f2dbd-127">Konvertieren von ServiceContract in einen GrpC-Dienst</span><span class="sxs-lookup"><span data-stu-id="f2dbd-127">Convert the ServiceContract to a gRPC service</span></span>

<span data-ttu-id="f2dbd-128">Die WCF-`Get`-Methode nimmt zwei Parameter an: `Guid traderId` und `int portfolioId`.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-128">The WCF `Get` method takes two parameters: `Guid traderId` and `int portfolioId`.</span></span> <span data-ttu-id="f2dbd-129">GrpC-Dienst Methoden können nur einen einzelnen Parameter verwenden, sodass eine Nachricht erstellt werden muss, um die beiden Werte aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-129">gRPC service methods can only take a single parameter, so a message must be created to hold the two values.</span></span> <span data-ttu-id="f2dbd-130">Es ist üblich, diese Anforderungs Objekte mit dem gleichen Namen wie die-Methode und das Suffix `Request`zu benennen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-130">It's common practice to name these request objects with the same name as the method and the suffix `Request`.</span></span> <span data-ttu-id="f2dbd-131">Auch hier wird `string` für das `traderId` Feld anstelle `Guid`verwendet.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-131">Again, `string` is being used for the `traderId` field instead of `Guid`.</span></span>

<span data-ttu-id="f2dbd-132">Der Dienst könnte nur eine `Portfolio` Nachricht direkt zurückgeben, aber dies kann sich in Zukunft auf die Abwärtskompatibilität auswirken.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-132">The service could just return a `Portfolio` message directly, but again, this could impact backward compatibility in the future.</span></span> <span data-ttu-id="f2dbd-133">Es empfiehlt sich, separate `Request` und `Response` Nachrichten für jede Methode in einem Dienst zu definieren, auch wenn viele von Ihnen momentan identisch sind. deklarieren Sie daher eine `GetResponse` Nachricht mit einem einzelnen `Portfolio` Feld.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-133">It's a good practice to define separate `Request` and `Response` messages for every method in a service, even if many of them are the same right now, so declare a `GetResponse` message with a single `Portfolio` field.</span></span>

<span data-ttu-id="f2dbd-134">Das folgende Beispiel zeigt die Deklaration der GrpC-Dienst Methode mithilfe der `GetRequest` Nachricht:</span><span class="sxs-lookup"><span data-stu-id="f2dbd-134">The following example shows the declaration of the gRPC service method using the `GetRequest` message:</span></span>

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

<span data-ttu-id="f2dbd-135">Die WCF-`GetAll`-Methode nimmt nur einen einzigen Parameter, `traderId`, auf. es kann vorkommen, dass eine `string` als Parametertyp angegeben werden kann, aber für GrpC ein definierter Nachrichtentyp erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-135">The WCF `GetAll` method only takes a single parameter, `traderId`, so it might seem that one could specify `string` as the parameter type, but gRPC requires a defined message type.</span></span> <span data-ttu-id="f2dbd-136">Durch diese Anforderung wird die Verwendung von benutzerdefinierten Nachrichten für alle Eingaben und Ausgaben für zukünftige Abwärtskompatibilität erzwungen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-136">This requirement helps to enforce the practice of using custom messages for all inputs and outputs, for future backward compatibility.</span></span>

<span data-ttu-id="f2dbd-137">Die WCF-Methode hat ebenfalls eine `List<Portfolio>`zurückgegeben, aber aus demselben Grund lässt Sie einfache Parametertypen nicht zu, da GrpC `repeated Portfolio` nicht als Rückgabetyp zulässt.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-137">The WCF method also returned a `List<Portfolio>`, but for the same reason it doesn't allow simple parameter types, gRPC won't allow `repeated Portfolio` as a return type.</span></span> <span data-ttu-id="f2dbd-138">Erstellen Sie stattdessen einen `GetAllResponse` Typ, um die Liste zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-138">Instead, create a `GetAllResponse` type to wrap the list.</span></span>

> [!WARNING]
> <span data-ttu-id="f2dbd-139">Möglicherweise sind Sie versucht, eine `PortfolioList` Nachricht oder ähnliches zu erstellen und Sie über mehrere Dienst Methoden hinweg zu verwenden, aber Sie sollten dieser Versuchung widerstehen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-139">You may be tempted to create a `PortfolioList` message or similar and use it across multiple service methods, but you should resist this temptation.</span></span> <span data-ttu-id="f2dbd-140">Es ist unmöglich zu wissen, wie sich die verschiedenen Methoden in einem Dienst in Zukunft weiterentwickeln können, sodass die Nachrichten spezifisch und ordnungsgemäß voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-140">It's impossible to know how the various methods on a service may evolve in the future, so keep their messages specific and cleanly separated.</span></span>

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

<span data-ttu-id="f2dbd-141">Wenn Sie Ihr Projekt mit diesen Änderungen speichern, wird das GrpC-Buildziel im Hintergrund ausgeführt und generiert alle protobuf-Nachrichten Typen und eine Basisklasse, die Sie erben können, um den Dienst zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-141">If you save your project with these changes, the gRPC build target will run in the background and generate all the Protobuf message types and a base class you can inherit to implement the service.</span></span>

<span data-ttu-id="f2dbd-142">Öffnen Sie die `Services/GreeterService.cs`-Klasse, und löschen Sie den Beispielcode.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-142">Open up the `Services/GreeterService.cs` class and delete the example code.</span></span> <span data-ttu-id="f2dbd-143">Nun können Sie die Portfolio Service-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-143">Now you can add the Portfolio service implementation.</span></span> <span data-ttu-id="f2dbd-144">Die generierte Basisklasse befindet sich im `Protos` Namespace und wird als eine schsted Klasse generiert.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-144">The generated base class will be in the `Protos` namespace and is generated as a nested class.</span></span> <span data-ttu-id="f2dbd-145">GrpC erstellt eine statische Klasse mit dem gleichen Namen wie der Dienst in der `.proto`-Datei und dann eine Basisklasse mit dem Suffix `Base` in dieser statischen Klasse, sodass der vollständige Bezeichner für den Basistyp `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`ist.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-145">gRPC creates a static class with the same name as the service in the `.proto` file, and then a base class with the suffix `Base` inside that static class, so the full identifier for the base type is `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span></span>

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

<span data-ttu-id="f2dbd-146">Die-Basisklasse deklariert `virtual` Methoden für `Get` und `GetAll`, die überschrieben werden können, um den-Dienst zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-146">The base class declares `virtual` methods for `Get` and `GetAll` that can be overridden to implement the service.</span></span> <span data-ttu-id="f2dbd-147">Die Methoden werden `virtual` anstatt `abstract`, sodass der Dienst einen expliziten GrpC-`Unimplemented` Statuscode zurückgeben kann, wenn Sie ihn nicht implementieren, ähnlich wie Sie möglicherweise eine `NotImplementedException` C# in regulärem Code auslösen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-147">The methods are `virtual` rather than `abstract` so that if you don't implement them, the service can return an explicit gRPC `Unimplemented` status code, much like you might throw a `NotImplementedException` in regular C# code.</span></span>

<span data-ttu-id="f2dbd-148">Die Signatur für alle unären GrpC-Dienst Methoden in ASP.net Core ist konsistent.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-148">The signature for all gRPC unary service methods in ASP.NET Core is consistent.</span></span> <span data-ttu-id="f2dbd-149">Es gibt zwei Parameter: der erste ist der Nachrichtentyp, der in der `.proto`-Datei deklariert ist, und der zweite ist ein `ServerCallContext`, der ähnlich wie der `HttpContext` von ASP.net Core funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-149">There are two parameters: the first is the message type declared in the `.proto` file, and the second is a `ServerCallContext` that works similarly to the `HttpContext` from ASP.NET Core.</span></span> <span data-ttu-id="f2dbd-150">Tatsächlich gibt es eine Erweiterungsmethode mit dem Namen `GetHttpContext` für die `ServerCallContext`-Klasse, die Sie verwenden können, um die zugrunde liegenden `HttpContext`zu erhalten, obwohl Sie Sie nicht häufig verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-150">In fact, there's an extension method called `GetHttpContext` on the `ServerCallContext` class that you can use to get the underlying `HttpContext`, although you shouldn't need to use it often.</span></span> <span data-ttu-id="f2dbd-151">Wir sehen uns die `ServerCallContext` weiter unten in diesem Kapitel und auch das Kapitel, in dem die Authentifizierung erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-151">We'll take a look at `ServerCallContext` later in this chapter, and also in the chapter that discusses authentication.</span></span>

<span data-ttu-id="f2dbd-152">Der Rückgabetyp der Methode ist eine `Task<T>`, wobei `T` der Antwort Nachrichtentyp ist.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-152">The method's return type is a `Task<T>` where `T` is the response message type.</span></span> <span data-ttu-id="f2dbd-153">Alle GrpC-Dienst Methoden sind asynchron.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-153">All gRPC service methods are asynchronous.</span></span>

## <a name="migrate-the-portfoliodata-library-to-net-core"></a><span data-ttu-id="f2dbd-154">Migrieren der videodata-Bibliothek zu .net Core</span><span class="sxs-lookup"><span data-stu-id="f2dbd-154">Migrate the PortfolioData library to .NET Core</span></span>

<span data-ttu-id="f2dbd-155">An diesem Punkt benötigt das Projekt das Portfolio-Repository und die Modelle, die in der `TraderSys.PortfolioData`-Klassenbibliothek in der WCF-Lösung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-155">At this point, the project needs the Portfolio repository and models contained in the `TraderSys.PortfolioData` class library in the WCF solution.</span></span> <span data-ttu-id="f2dbd-156">Die einfachste Möglichkeit, Sie zu übernehmen, besteht darin, eine neue Klassenbibliothek zu erstellen, indem Sie entweder das Visual Studio-Dialogfeld " **Neues Projekt** " mit der Vorlage für die *Klassenbibliothek (.NET Standard)* verwenden, oder über die Befehlszeile mithilfe des .net Core-CLI die folgenden Befehle aus dem Verzeichnis mit der `TraderSys.sln`-Datei ausführen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-156">The easiest way to bring them across is to create a new class library using either the Visual Studio **New project** dialog with the *Class Library (.NET Standard)* template, or from the command line using the .NET Core CLI, running the following commands from the directory containing the `TraderSys.sln` file.</span></span>

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

<span data-ttu-id="f2dbd-157">Nachdem die Bibliothek erstellt und der Projekt Mappe hinzugefügt wurde, löschen Sie die generierte `Class1.cs` Datei und kopieren die Dateien aus der Bibliothek der WCF-Projekt Mappe in den Ordner der neuen Klassenbibliothek, wobei die Ordnerstruktur beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-157">Once the library has been created and added to the solution, delete the generated `Class1.cs` file and copy the files from the WCF solution's library into the new class library's folder, keeping the folder structure.</span></span>

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

<span data-ttu-id="f2dbd-158">.Net-Projekte im SDK-Stil enthalten automatisch alle `.cs` Dateien in oder in Ihrem eigenen Verzeichnis, sodass es nicht erforderlich ist, Sie explizit dem Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-158">SDK-style .NET projects automatically include any `.cs` files in or under their own directory, so there's no need to explicitly add them to the project.</span></span> <span data-ttu-id="f2dbd-159">Der einzige Schritt besteht darin, die Attribute "`DataContract`" und "`DataMember`" aus den Klassen `Portfolio` und `PortfolioItem` zu entfernen C# , sodass Sie einfache Klassen sind.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-159">The only step remaining is to remove the `DataContract` and `DataMember` attributes from the `Portfolio` and `PortfolioItem` classes so they're plain old C# classes.</span></span>

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

## <a name="use-aspnet-core-dependency-injection"></a><span data-ttu-id="f2dbd-160">Verwenden von ASP.net Core-Abhängigkeitsinjektion</span><span class="sxs-lookup"><span data-stu-id="f2dbd-160">Use ASP.NET Core dependency injection</span></span>

<span data-ttu-id="f2dbd-161">Nun können Sie dem GrpC-Anwendungsprojekt einen Verweis auf diese Bibliothek hinzufügen und die `PortfolioRepository` Klasse mithilfe der Abhängigkeitsinjektion in der GrpC-Dienst Implementierung nutzen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-161">Now you can add a reference to this library to the gRPC application project and consume the `PortfolioRepository` class using dependency injection in the gRPC service implementation.</span></span> <span data-ttu-id="f2dbd-162">In der WCF-Anwendung wurde die Abhängigkeitsinjektion vom autofac IOC-Container bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-162">In the WCF application, dependency injection was provided by the Autofac IoC container.</span></span> <span data-ttu-id="f2dbd-163">In ASP.net Core wurde eine Abhängigkeitsinjektion in integriert. das Repository kann in der `ConfigureServices`-Methode in der `Startup`-Klasse registriert werden.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-163">ASP.NET Core has dependency injection baked in; the repository can be registered in the `ConfigureServices` method in the `Startup` class.</span></span>

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

<span data-ttu-id="f2dbd-164">Die `IPortfolioRepository`-Implementierung kann nun wie folgt als Konstruktorparameter in der `PortfolioService`-Klasse angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="f2dbd-164">The `IPortfolioRepository` implementation can now be specified as a constructor parameter in the `PortfolioService` class, as follows:</span></span>

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

## <a name="implement-the-grpc-service"></a><span data-ttu-id="f2dbd-165">Implementieren des GrpC-Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="f2dbd-165">Implement the gRPC service</span></span>

<span data-ttu-id="f2dbd-166">Nachdem Sie die Nachrichten und ihren Dienst in der `portfolios.proto`-Datei deklariert haben, müssen Sie die Dienst Methoden in der `PortfolioService`-Klasse implementieren, die von der vom GrpC generierten `Portfolios.PortfoliosBase`-Klasse erbt.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-166">Now that you've declared your messages and your service in the `portfolios.proto` file, you have to implement the service methods in the `PortfolioService` class that inherits from the gRPC-generated `Portfolios.PortfoliosBase` class.</span></span> <span data-ttu-id="f2dbd-167">Die Methoden werden als `virtual` in der Basisklasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-167">The methods are declared as `virtual` in the base class.</span></span> <span data-ttu-id="f2dbd-168">Wenn Sie Sie nicht überschreiben, geben Sie standardmäßig den Statuscode "nicht implementiert" von GrpC zurück.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-168">If you don't override them, they'll return a gRPC "Not Implemented" status code by default.</span></span>

<span data-ttu-id="f2dbd-169">Beginnen Sie, indem Sie die `Get`-Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-169">Start by implementing the `Get` method.</span></span> <span data-ttu-id="f2dbd-170">Die Standard Überschreibung sieht wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="f2dbd-170">The default override looks like the following example:</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

<span data-ttu-id="f2dbd-171">Das erste Problem besteht darin, dass `request.TraderId` eine Zeichenfolge ist und dass der Dienst eine `Guid`erfordert.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-171">The first issue is that `request.TraderId` is a string, and the service requires a `Guid`.</span></span> <span data-ttu-id="f2dbd-172">Obwohl das erwartete Format für die Zeichenfolge eine `UUID`ist, muss der Code die Möglichkeit behandeln, dass ein Aufrufer einen ungültigen Wert gesendet hat und entsprechend antwortet.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-172">Even though the expected format for the string is a `UUID`, the code has to deal with the possibility that a caller has sent an invalid value and respond appropriately.</span></span> <span data-ttu-id="f2dbd-173">Der Dienst kann mit Fehlern Antworten, indem er eine `RpcException`auslöst und den standardmäßigen `InvalidArgument` Statuscode verwendet, um das Problem auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-173">The service can respond with errors by throwing an `RpcException`, and use the standard `InvalidArgument` status code to express the problem.</span></span>

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

<span data-ttu-id="f2dbd-174">Wenn für `traderId`ein geeigneter `Guid` Wert vorhanden ist, kann das Repository zum Abrufen des Portfolios verwendet und an den Client zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-174">Once there's a proper `Guid` value for `traderId`, the repository can be used to retrieve the Portfolio and return it to the client.</span></span>

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a><span data-ttu-id="f2dbd-175">Zuordnen interner Modelle zu GrpC-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="f2dbd-175">Map internal models to gRPC messages</span></span>

<span data-ttu-id="f2dbd-176">Der vorherige Code funktioniert nicht tatsächlich, weil das Repository sein eigenes poco-Modell `Portfolio`zurückgibt, aber GrpC benötigt *seine* eigene protobuf-Nachricht `Portfolio`.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-176">The previous code doesn't actually work because the repository is returning its own POCO model `Portfolio`, but gRPC needs *its* own Protobuf message `Portfolio`.</span></span> <span data-ttu-id="f2dbd-177">Ähnlich wie bei der Zuordnung von Entity Framework Typen zu Daten Übertragungs Typen besteht die beste Lösung darin, eine Konvertierung zwischen beiden zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-177">Much like mapping Entity Framework types to data transfer types, the best solution is to provide conversion between the two.</span></span> <span data-ttu-id="f2dbd-178">Ein guter Ort zum Einfügen des Codes ist die von protobuf generierte Klasse, die als `partial`-Klasse deklariert wird, sodass Sie erweitert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-178">A good place to put the code for this is in the Protobuf-generated class, which is declared as a `partial` class so it can be extended.</span></span>

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
> <span data-ttu-id="f2dbd-179">Sie können eine Bibliothek wie [AutoMapper](https://automapper.org/) verwenden, um diese Konvertierung von internen Modellklassen in protobuf-Typen zu verarbeiten, solange Sie die Typkonvertierungen auf niedrigerer Ebene wie `string`/`Guid` oder `decimal`/`double` und die Listen Zuordnung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-179">You could use a library like [AutoMapper](https://automapper.org/) to handle this conversion from internal model classes to Protobuf types, as long as you configure the lower-level type conversions like `string`/`Guid` or `decimal`/`double` and the list mapping.</span></span>

<span data-ttu-id="f2dbd-180">Wenn der Konvertierungs Code vorhanden ist, kann die Implementierung der `Get` Methode abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-180">With the conversion code in place, the `Get` method implementation can be completed.</span></span>

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

<span data-ttu-id="f2dbd-181">Die Implementierung der `GetAll`-Methode ist ähnlich.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-181">The implementation of the `GetAll` method is similar.</span></span> <span data-ttu-id="f2dbd-182">Beachten Sie, dass die `repeated` Felder für protobuf-Nachrichten als `readonly` Eigenschaften vom Typ `RepeatedField<T>`generiert werden. Daher müssen Sie Elemente mithilfe der `AddRange`-Methode hinzufügen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f2dbd-182">Note that the `repeated` fields on Protobuf messages are generated as `readonly` properties of type `RepeatedField<T>`, so you have to add items to them using the `AddRange` method, like in the following example:</span></span>

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

<span data-ttu-id="f2dbd-183">Nachdem Sie den WCF-Anforderungs-/Antwortdienst erfolgreich zu GrpC migriert haben, sehen wir uns an, wie Sie einen Client für ihn aus der `.proto` Datei erstellen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-183">Having successfully migrated the WCF request-reply service to gRPC, let's look at creating a client for it from the `.proto` file.</span></span>

## <a name="generate-client-code"></a><span data-ttu-id="f2dbd-184">Generieren von Client Code</span><span class="sxs-lookup"><span data-stu-id="f2dbd-184">Generate client code</span></span>

<span data-ttu-id="f2dbd-185">Erstellen Sie eine .NET Standard-Klassenbibliothek in der gleichen Projekt Mappe, die den-Client enthält.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-185">Create a .NET Standard class library in the same solution to contain the client.</span></span> <span data-ttu-id="f2dbd-186">Dies ist in erster Linie ein Beispiel für das Erstellen von Client Code, aber Sie könnten eine solche Bibliothek mithilfe von nuget Verpacken und Sie in einem internen Repository verteilen, damit andere .NET-Teams Sie nutzen können.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-186">This is primarily an example of creating client code, but you could package such a library using NuGet and distribute it on an internal repository for other .NET teams to consume.</span></span> <span data-ttu-id="f2dbd-187">Fügen Sie der Projekt Mappe eine neue .NET Standard-Klassenbibliothek mit dem Namen `TraderSys.Portfolios.Client` hinzu, und löschen Sie die `Class1.cs` Datei.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-187">Go ahead and add a new .NET Standard Class Library called `TraderSys.Portfolios.Client` to the solution and delete the `Class1.cs` file.</span></span>

> [!CAUTION]
> <span data-ttu-id="f2dbd-188">Das nuget-Paket " [GrpC .net. Client](https://www.nuget.org/packages/Grpc.Net.Client) " erfordert .net Core 3,0 (oder eine andere .NET Standard 2,1-kompatible Laufzeit).</span><span class="sxs-lookup"><span data-stu-id="f2dbd-188">The [Grpc.Net.Client](https://www.nuget.org/packages/Grpc.Net.Client) NuGet package requires .NET Core 3.0 (or another .NET Standard 2.1-compliant runtime).</span></span> <span data-ttu-id="f2dbd-189">Frühere Versionen von .NET Framework und .net Core werden vom nuget-Paket " [GrpC. Core](https://www.nuget.org/packages/Grpc.Core) " unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-189">Earlier versions of .NET Framework and .NET Core are supported by the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core) NuGet package.</span></span>

<span data-ttu-id="f2dbd-190">In Visual Studio 2019 können Sie in früheren Versionen von Visual Studio Verweise auf GrpC-Dienste hinzufügen, ähnlich wie in früheren Versionen von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-190">In Visual Studio 2019, you can add references to gRPC services similar to the way you'd add Service References to WCF projects in earlier versions of Visual Studio.</span></span> <span data-ttu-id="f2dbd-191">Dienst Verweise und verbundene Dienste werden jetzt auf der gleichen Benutzeroberfläche verwaltet, auf die Sie zugreifen können, indem Sie mit der rechten Maustaste auf den Knoten **Abhängigkeiten** im Projekt `TraderSys.Portfolios.Client` in Projektmappen-Explorer klicken und **verbundenen Dienst hinzufügen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-191">Service References and Connected Services are all managed under the same UI now, which you can access by right-clicking the **Dependencies** node in the `TraderSys.Portfolios.Client` project in Solution Explorer and selecting **Add Connected Service**.</span></span> <span data-ttu-id="f2dbd-192">Wählen Sie im angezeigten Tool Fenster den Abschnitt **Dienst Verweise** aus, und klicken Sie auf **neuen GrpC-Dienst Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-192">In the tool window that appears, select the **Service References** section and click **Add new gRPC service reference**.</span></span>

![Die verbundene Dienste-Benutzeroberfläche in Visual Studio 2019](media/migrate-request-reply/add-connected-service.png)

<span data-ttu-id="f2dbd-194">Navigieren Sie zur `portfolios.proto`-Datei im Projekt `TraderSys.Portfolios`, belassen Sie den **Typ der zu generierenden Klasse** als **Client**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-194">Browse to the `portfolios.proto` file in the `TraderSys.Portfolios` project, leave the **type of class to be generated** as **Client**, and click **OK**.</span></span>

![Dialogfeld "Hinzufügen eines neuen GrpC-Dienst Verweises" in Visual Studio 2019](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> <span data-ttu-id="f2dbd-196">Beachten Sie, dass dieses Dialogfeld auch ein URL-Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-196">Notice that this dialog also provides a URL field.</span></span> <span data-ttu-id="f2dbd-197">Wenn Ihre Organisation ein Verzeichnis `.proto` Dateien, auf das zugegriffen werden kann, verwaltet, können Sie Clients erstellen, indem Sie einfach diese URL-Adresse festlegen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-197">If your organization maintains a web-accessible directory of `.proto` files, you can create clients just by setting this URL address.</span></span>

<span data-ttu-id="f2dbd-198">Wenn Sie die Funktion " **verbundenen Dienst hinzufügen** " von Visual Studio verwenden, wird die `portfolios.proto`-Datei dem Klassen Bibliotheksprojekt als *verknüpfte Datei*hinzugefügt und nicht als kopiert, sodass Änderungen an der Datei im Dienstprojekt automatisch im Client Projekt angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-198">When using the Visual Studio **Add Connected Service** feature, the `portfolios.proto` file is added to the Class Library project as a *linked file*, rather than copied, so changes to the file in the service project will automatically be applied in the client project.</span></span> <span data-ttu-id="f2dbd-199">Das `<Protobuf>`-Element in der `csproj` Datei sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f2dbd-199">The `<Protobuf>` element in the `csproj` file looks like this:</span></span>

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> <span data-ttu-id="f2dbd-200">Wenn Sie Visual Studio nicht verwenden oder von der Befehlszeile aus arbeiten möchten, können Sie das Tool **dotnet-GrpC** Global verwenden, um protobuf-Verweise in einem .net-GrpC-Projekt zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-200">If you are not using Visual Studio or prefer to work from the command line, you can use the **dotnet-grpc** global tool to manage Protobuf references within a .NET gRPC project.</span></span> <span data-ttu-id="f2dbd-201">[Weitere Informationen finden Sie in der Dokumentation zu **dotnet-GrpC** ](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc).</span><span class="sxs-lookup"><span data-stu-id="f2dbd-201">[Refer to the **dotnet-grpc** documentation for more information](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc).</span></span>

### <a name="use-the-portfolios-service-from-a-client-application"></a><span data-ttu-id="f2dbd-202">Verwenden des Portfolios-Dienstanbieter aus einer Client Anwendung</span><span class="sxs-lookup"><span data-stu-id="f2dbd-202">Use the Portfolios service from a client application</span></span>

<span data-ttu-id="f2dbd-203">Der folgende Code ist ein kurzes Beispiel für die Verwendung des generierten Clients in einer Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-203">The following code is a brief example of using the generated client in a console application.</span></span> <span data-ttu-id="f2dbd-204">Eine ausführlichere Untersuchung des GrpC-Client Codes finden Sie am Ende dieses Kapitels.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-204">A more detailed exploration of the gRPC client code is at the end of this chapter.</span></span>

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

<span data-ttu-id="f2dbd-205">Nun haben Sie eine einfache WCF-Anwendung zu einem ASP.net Core GrpC-Dienst migriert und einen Client erstellt, um den Dienst aus einer .NET-Anwendung zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-205">Now, you've migrated a basic WCF application to an ASP.NET Core gRPC service and created a client to consume the service from a .NET application.</span></span> <span data-ttu-id="f2dbd-206">Im nächsten Abschnitt werden die mehr beteiligten "Duplex Dienste" behandelt.</span><span class="sxs-lookup"><span data-stu-id="f2dbd-206">The next section will cover the more involved "duplex" services.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f2dbd-207">[Zurück](create-project.md)
>[Weiter](migrate-duplex-services.md)</span><span class="sxs-lookup"><span data-stu-id="f2dbd-207">[Previous](create-project.md)
[Next](migrate-duplex-services.md)</span></span>
