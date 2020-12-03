---
title: 'Breaking Change: HTTP: HttpClient-Instanzen, die von IHttpClientFactory erstellt wurden, protokollieren Integerstatuscodes'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „HTTP: HttpClient-Instanzen, die von IHttpClientFactory erstellt wurden, protokollieren Integerstatuscodes'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 964c0a65a07816acea8016d42a66a6bf84aba7c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759204"
---
# <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a>HTTP: HttpClient-Instanzen, die von IHttpClientFactory erstellt wurden, protokollieren Integerstatuscodes

<xref:System.Net.Http.HttpClient>-Instanzen, die durch <xref:System.Net.Http.IHttpClientFactory> erstellt werden, protokollieren HTTP-Statuscodes als Integerwerte anstatt als Statuscodenamen.

## <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 1

## <a name="old-behavior"></a>Altes Verhalten

Bei der Protokollierung werden die Textbeschreibungen der HTTP-Statuscodes verwendet. Sehen Sie sich die folgenden Protokollmeldungen an:

```output
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

## <a name="new-behavior"></a>Neues Verhalten

Bei der Protokollierung werden die Integerwerte der HTTP-Statuscodes verwendet. Sehen Sie sich die folgenden Protokollmeldungen an:

```output
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

## <a name="reason-for-change"></a>Grund für die Änderung

Das ursprüngliche Verhalten dieser Protokollierung ist nicht mit anderen Komponenten von ASP.NET Core konsistent, die standardmäßig Integerwerte verwenden. Die Inkonsistenz bewirkt, dass Protokolle über strukturierte Protokollierungssysteme wie [Elasticsearch](https://www.elastic.co/elasticsearch/) schwierig abgefragt werden können. Weitere Informationen finden Sie unter [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).

Die Verwendung von Integerwerten bietet mehr Flexibilität als die Verwendung von Textwerten, da so Abfragen für Wertebereiche möglich sind.

Wir haben auch überlegt, einen weiteren Protokollwerts zum Erfassen des Integerstatuscodes hinzuzufügen. Leider würde das zu einer weiteren Inkonsistenz mit dem Rest von ASP.NET Core führen. Die HttpClient-Protokollierung und die HTTP-Server- und -Hostingprotokollierung verwenden bereits den gleichen `StatusCode`-Schlüsselnamen.

## <a name="recommended-action"></a>Empfohlene Aktion

Die beste Option besteht darin, Protokollierungsabfragen zu aktualisieren, damit die Integerwerte der Statuscodes verwendet werden. Diese Methode kann das Schreiben von Abfragen für mehrere ASP.NET Core-Versionen erschweren. Die Verwendung von Integerwerten für diesen Zweck ist jedoch viel flexibler für das Abfragen von Protokollen.

Wenn Sie die Kompatibilität mit dem alten Verhaltensweisen erzwingen und Textstatuscodes verwenden müssen, ersetzen Sie die `IHttpClientFactory`-Protokollierung durch ihre eigene:

1. Kopieren Sie die .NET Core 3.1-Versionen der folgenden Klassen in Ihr Projekt:

    * [LoggingHttpMessageHandlerBuilderFilter](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [LoggingHttpMessageHandler](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [LoggingScopeHttpMessageHandler](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [HttpHeadersLogValue](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. Benennen Sie die Klassen um, um Konflikte mit öffentlichen Typen im NuGet-Paket [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) zu vermeiden.

1. Ersetzen Sie die integrierte Implementierung von `LoggingHttpMessageHandlerBuilderFilter` in der `Startup.ConfigureServices`-Methode des Projekts durch ihre eigene. Zum Beispiel:

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

## <a name="affected-apis"></a>Betroffene APIs

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:System.Net.Http.HttpClient`

-->
