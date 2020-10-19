---
ms.openlocfilehash: f1556fac0e8aa79c87cd5e74c1b603582ff5db1b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160539"
---
### <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a><span data-ttu-id="851cb-101">HTTP: HttpClient-Instanzen, die von IHttpClientFactory erstellt wurden, protokollieren Integerstatuscodes</span><span class="sxs-lookup"><span data-stu-id="851cb-101">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>

<span data-ttu-id="851cb-102"><xref:System.Net.Http.HttpClient>-Instanzen, die durch <xref:System.Net.Http.IHttpClientFactory> erstellt werden, protokollieren HTTP-Statuscodes als Integerwerte anstatt als Statuscodenamen.</span><span class="sxs-lookup"><span data-stu-id="851cb-102"><xref:System.Net.Http.HttpClient> instances created by <xref:System.Net.Http.IHttpClientFactory> log HTTP status codes as integers instead of with status code names.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="851cb-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="851cb-103">Version introduced</span></span>

<span data-ttu-id="851cb-104">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="851cb-104">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="851cb-105">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="851cb-105">Old behavior</span></span>

<span data-ttu-id="851cb-106">Bei der Protokollierung werden die Textbeschreibungen der HTTP-Statuscodes verwendet.</span><span class="sxs-lookup"><span data-stu-id="851cb-106">Logging uses the textual descriptions of HTTP status codes.</span></span> <span data-ttu-id="851cb-107">Sehen Sie sich die folgenden Protokollmeldungen an:</span><span class="sxs-lookup"><span data-stu-id="851cb-107">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

#### <a name="new-behavior"></a><span data-ttu-id="851cb-108">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="851cb-108">New behavior</span></span>

<span data-ttu-id="851cb-109">Bei der Protokollierung werden die Integerwerte der HTTP-Statuscodes verwendet.</span><span class="sxs-lookup"><span data-stu-id="851cb-109">Logging uses the integer values of HTTP status codes.</span></span> <span data-ttu-id="851cb-110">Sehen Sie sich die folgenden Protokollmeldungen an:</span><span class="sxs-lookup"><span data-stu-id="851cb-110">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

#### <a name="reason-for-change"></a><span data-ttu-id="851cb-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="851cb-111">Reason for change</span></span>

<span data-ttu-id="851cb-112">Das ursprüngliche Verhalten dieser Protokollierung ist nicht mit anderen Komponenten von ASP.NET Core konsistent, die standardmäßig Integerwerte verwenden.</span><span class="sxs-lookup"><span data-stu-id="851cb-112">The original behavior of this logging is inconsistent with other parts of ASP.NET Core that have always used integer values.</span></span> <span data-ttu-id="851cb-113">Die Inkonsistenz bewirkt, dass Protokolle über strukturierte Protokollierungssysteme wie [Elasticsearch](https://www.elastic.co/elasticsearch/) schwierig abgefragt werden können.</span><span class="sxs-lookup"><span data-stu-id="851cb-113">The inconsistency makes logs difficult to query via structured logging systems such as [Elasticsearch](https://www.elastic.co/elasticsearch/).</span></span> <span data-ttu-id="851cb-114">Weitere Informationen finden Sie unter [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span><span class="sxs-lookup"><span data-stu-id="851cb-114">For more context, see [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span></span>

<span data-ttu-id="851cb-115">Die Verwendung von Integerwerten bietet mehr Flexibilität als die Verwendung von Textwerten, da so Abfragen für Wertebereiche möglich sind.</span><span class="sxs-lookup"><span data-stu-id="851cb-115">Using integer values is more flexible than text because it allows queries on ranges of values.</span></span>

<span data-ttu-id="851cb-116">Wir haben auch überlegt, einen weiteren Protokollwerts zum Erfassen des Integerstatuscodes hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="851cb-116">Adding another log value to capture the integer status code was considered.</span></span> <span data-ttu-id="851cb-117">Leider würde das zu einer weiteren Inkonsistenz mit dem Rest von ASP.NET Core führen.</span><span class="sxs-lookup"><span data-stu-id="851cb-117">Unfortunately, doing so would introduce another inconsistency with the rest of ASP.NET Core.</span></span> <span data-ttu-id="851cb-118">Die HttpClient-Protokollierung und die HTTP-Server- und -Hostingprotokollierung verwenden bereits den gleichen `StatusCode`-Schlüsselnamen.</span><span class="sxs-lookup"><span data-stu-id="851cb-118">HttpClient logging and HTTP server/hosting logging use the same `StatusCode` key name already.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="851cb-119">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="851cb-119">Recommended action</span></span>

<span data-ttu-id="851cb-120">Die beste Option besteht darin, Protokollierungsabfragen zu aktualisieren, damit die Integerwerte der Statuscodes verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="851cb-120">The best option is to update logging queries to use the integer values of status codes.</span></span> <span data-ttu-id="851cb-121">Diese Methode kann das Schreiben von Abfragen für mehrere ASP.NET Core-Versionen erschweren.</span><span class="sxs-lookup"><span data-stu-id="851cb-121">This option may cause some difficulty writing queries across multiple ASP.NET Core versions.</span></span> <span data-ttu-id="851cb-122">Die Verwendung von Integerwerten für diesen Zweck ist jedoch viel flexibler für das Abfragen von Protokollen.</span><span class="sxs-lookup"><span data-stu-id="851cb-122">However, using integers for this purpose is much more flexible for querying logs.</span></span>

<span data-ttu-id="851cb-123">Wenn Sie die Kompatibilität mit dem alten Verhaltensweisen erzwingen und Textstatuscodes verwenden müssen, ersetzen Sie die `IHttpClientFactory`-Protokollierung durch ihre eigene:</span><span class="sxs-lookup"><span data-stu-id="851cb-123">If you need to force compatibility with the old behavior and use textual status codes, replace the `IHttpClientFactory` logging with your own:</span></span>

1. <span data-ttu-id="851cb-124">Kopieren Sie die .NET Core 3.1-Versionen der folgenden Klassen in Ihr Projekt:</span><span class="sxs-lookup"><span data-stu-id="851cb-124">Copy the .NET Core 3.1 versions of the following classes into your project:</span></span>

    * [<span data-ttu-id="851cb-125">LoggingHttpMessageHandlerBuilderFilter</span><span class="sxs-lookup"><span data-stu-id="851cb-125">LoggingHttpMessageHandlerBuilderFilter</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [<span data-ttu-id="851cb-126">LoggingHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="851cb-126">LoggingHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [<span data-ttu-id="851cb-127">LoggingScopeHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="851cb-127">LoggingScopeHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [<span data-ttu-id="851cb-128">HttpHeadersLogValue</span><span class="sxs-lookup"><span data-stu-id="851cb-128">HttpHeadersLogValue</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. <span data-ttu-id="851cb-129">Benennen Sie die Klassen um, um Konflikte mit öffentlichen Typen im NuGet-Paket [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="851cb-129">Rename the classes to avoid conflicts with public types in the [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) NuGet package.</span></span>

1. <span data-ttu-id="851cb-130">Ersetzen Sie die integrierte Implementierung von `LoggingHttpMessageHandlerBuilderFilter` in der `Startup.ConfigureServices`-Methode des Projekts durch ihre eigene.</span><span class="sxs-lookup"><span data-stu-id="851cb-130">Replace the built-in implementation of `LoggingHttpMessageHandlerBuilderFilter` with your own in the project's `Startup.ConfigureServices` method.</span></span> <span data-ttu-id="851cb-131">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="851cb-131">For example:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        // Other service registrations go first. Code omitted for brevity.

        // Place the following after all AddHttpClient registrations.
        services.RemoveAll<IHttpMessageHandlerBuilderFilter>();

        services.AddSingleton<IHttpMessageHandlerBuilderFilter,
                              MyLoggingHttpMessageHandlerBuilderFilter>();
    }
    ```

#### <a name="category"></a><span data-ttu-id="851cb-132">Kategorie</span><span class="sxs-lookup"><span data-stu-id="851cb-132">Category</span></span>

<span data-ttu-id="851cb-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="851cb-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="851cb-134">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="851cb-134">Affected APIs</span></span>

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:System.Net.Http.HttpClient`

-->
