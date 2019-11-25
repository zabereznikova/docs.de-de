---
title: Wann sollte .NET Framework für Docker-Container verwendet werden?
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Wann sollte .NET Framework für Docker-Container verwendet werden?
ms.date: 01/07/2019
ms.openlocfilehash: 9e5b18e8e3482eb86c0d9dea5de56fb12f9d6256
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966889"
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Wann sollte .NET Framework für Docker-Container verwendet werden?

Während .NET Core erhebliche Vorteile für neue Anwendungen und Anwendungsmuster bietet, ist .NET Framework nach wie vor eine gute Wahl für viele vorhandene Szenarios.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Direktes Migrieren vorhandener Anwendungen zu einem Windows Server-Container

Mithilfe von Docker-Containern können Sie die Bereitstellung vereinfachen, auch wenn Sie keine Microservices erstellen. Wenn Sie beispielsweise den DevOps-Workflow mit Docker verbessern möchten, bieten Container besser isolierte Testumgebungen und können Bereitstellungsprobleme lösen, die durch fehlende Abhängigkeiten verursacht werden, wenn Sie in eine Produktionsumgebung wechseln. Wenn Sie eine monolithische Anwendung bereitstellen, ist es in solchen Fällen sinnvoll, Docker- und Windows-Container für die aktuellen .NET Framework-Anwendungen zu verwenden.

In diesem Szenario müssen Sie Ihre vorhandenen Anwendungen in den meisten Fällen nicht zu .NET Core migrieren, sondern können einfach Docker-Container verwenden, die das traditionelle .NET Framework enthalten. Empfohlen wird jedoch, .NET Core zu verwenden, wenn Sie eine vorhandene Anwendung erweitern möchten, z.B. durch Schreiben eines neuen Diensts in ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Verwenden von .NET-Bibliotheken von Drittanbietern oder NuGet-Paketen, die für .NET Core nicht verfügbar sind

[.NET Standard](../../../standard/net-standard.md) kommt in Drittanbieterbibliotheken immer häufiger zum Einsatz und ermöglicht die Codefreigabe in allen .NET-Varianten, einschließlich .NET Core. In .NET Standard 2.0 und höher wurde die API-Oberflächenkompatibilität frameworkübergreifend deutlich erhöht, und Anwendungen können in .NET Core 2.x auch direkt auf vorhandene .NET Framework-Bibliotheken verweisen (siehe [.NET Framework 4.6.1 supporting .NET Standard 2.0](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#net-framework-461-supporting-net-standard-20), .NET Framework 4.6.1 mit Unterstützung für .NET Standard 2.0).

Darüber hinaus wurde das [Windows Compatibility Pack](../../../core/porting/windows-compat-pack.md) im November 2017 veröffentlicht, um die für .NET Standard 2.0 unter Windows verfügbare API-Oberfläche zu erweitern. Mit diesem Paket kann der größte Teil des vorhandenen Codes mit nur geringen oder ganz ohne Änderungen für .NET Standard 2.x neu kompiliert und unter Windows ausgeführt werden.

Selbst bei diesen außergewöhnlichen Fortschritten seit .NET Standard 2.0 und .NET Core 2.1 können jedoch weiterhin Fälle auftreten, in denen bestimmte NuGet-Pakete nicht ohne Windows ausgeführt werden können und .NET Core nicht unterstützen. Wenn diese Pakete von entscheidender Bedeutung für die Anwendung sind, müssen Sie .NET Framework in Windows-Containern verwenden.

## <a name="using-net-technologies-not-available-for-net-core"></a>Verwenden von .NET-Technologien, die für .NET Core nicht verfügbar sind

Einige .NET Framework-Technologien sind nicht in der aktuellen Version von .NET Core verfügbar (Version 2.2 bei Redaktionsschluss). Einige werden in höheren .NET Core-Versionen verfügbar sein (.NET Core 2.x). Andere können jedoch nicht für die neuen Anwendungsmuster verwendet werden, auf die .NET Core ausgelegt ist, und werden möglicherweise nie verfügbar sein.

In der folgenden Liste wird der Großteil der Technologien aufgezählt, die in .NET Core 2.x nicht verfügbar sind:

- ASP.NET Web Forms: Diese Technologie ist nur in .NET Framework verfügbar. Eine Integration von ASP.NET Web Forms in .NET Core ist zurzeit nicht geplant.

- WCF-Dienste: Auch wenn eine [WCF-Clientbibliothek](https://github.com/dotnet/wcf) für die Nutzung durch WCF-Dienste von .NET Core verfügbar ist, ist die WCF-Serverimplementierung seit Mitte 2017 nur in .NET Framework verfügbar. Dieses Szenario kann für zukünftige Versionen von .NET Core eine Rolle spielen, es gibt sogar Erwägungen, bestimmte APIs in das [Windows Compatibility Pack](../../../core/porting/windows-compat-pack.md) aufzunehmen.

- Workflow-bezogene Dienste: Windows Workflow Foundation (WF), die Workflow-Dienste (WCF + WF in einem einzigen Dienst) und WCF Data Services (früher ADO.NET Data Services) sind nur in .NET Framework verfügbar. Es ist zurzeit nicht vorgesehen, sie in .NET Core zu integrieren.

Zusätzlich zu den in der offiziellen [Roadmap für .NET Core](https://github.com/aspnet/Home/wiki/Roadmap) aufgeführten Technologien werden möglicherweise andere Features zu .NET Core portiert. Eine vollständige Liste finden Sie auf der GitHub-CoreFX-Website. Die Elemente sind jeweils mit dem Tag [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) versehen. Beachten Sie, dass diese Liste keine Zusage von Microsoft darstellt, dass diese Komponenten in .NET Core integriert werden. In dieser Liste werden lediglich Anregungen der Community erfasst. Wenn Sie sich für eine der oben aufgeführten Komponenten interessieren, können Sie sich gern auf GitHub an den Diskussionen beteiligen. Wenn Ihrer Ansicht nach noch etwas fehlt, [eröffnen Sie im CoreFX Repository ein neues „Issue“](https://github.com/dotnet/corefx/issues/new).

Zwar wird .NET Core 3 (zum Zeitpunkt der Erstellung dieses Texts in Arbeit) Unterstützung für eine große Zahl vorhandener .NET Framework-APIs beinhalten, diese sind aber desktoporientiert und bieten daher zurzeit keinen Nutzen in der Welt der Container.

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>Verwenden einer Plattform oder API, die .NET Core nicht unterstützt

Einige Plattformen von Microsoft oder Drittanbietern unterstützen .NET Core nicht. Einige Azure-Dienste stellen beispielsweise ein SDK bereit, das noch nicht für die Nutzung in .NET Core verfügbar ist. Dieses Problem ist jedoch nur vorübergehend, da alle Azure-Dienste letztendlich .NET Core verwenden werden. Das [Azure DocumentDB SDK für .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core) wurde z.B. als Vorschauversion am 16. November 2016 veröffentlicht und ist jetzt als stabile Version allgemein verfügbar.

Wenn eine der Plattformen oder einer der Dienste in Azure .NET Core weiterhin nicht mit der Client-API unterstützt, können Sie in der Zwischenzeit die entsprechende REST-API aus dem Azure-Dienst oder das Client SDK in .NET Framework verwenden.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Leitfaden für .NET Core** \
  [https://docs.microsoft.com/dotnet/core/index](../../../core/index.md)

- **Porting from .NET Framework to .NET Core (Portieren von .NET Framework zu .NET Core)** \
  [https://docs.microsoft.com/dotnet/core/porting/index](../../../core/porting/index.md)

- **Einführung zu .NET und Docker** \
  [https://docs.microsoft.com/dotnet/core/docker/introduction](../../../core/docker/introduction.md)

- **.NET-Komponenten – Übersicht** \
  [https://docs.microsoft.com/dotnet/standard/components](../../../standard/components.md)

>[!div class="step-by-step"]
>[Zurück](net-core-container-scenarios.md)
>[Weiter](container-framework-choice-factors.md)
