---
title: Wann sollte .NET Framework für Docker-Container verwendet werden?
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Wann sollte .NET Framework für Docker-Container verwendet werden?
ms.date: 01/30/2020
ms.openlocfilehash: 2697ae56eda104a0ee8e7bfcd79d3972943d1f79
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344996"
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Wann sollte .NET Framework für Docker-Container verwendet werden?

Während .NET Core erhebliche Vorteile für neue Anwendungen und Anwendungsmuster bietet, ist .NET Framework nach wie vor eine gute Wahl für viele vorhandene Szenarios.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Direktes Migrieren vorhandener Anwendungen zu einem Windows Server-Container

Mithilfe von Docker-Containern können Sie die Bereitstellung vereinfachen, auch wenn Sie keine Microservices erstellen. Wenn Sie beispielsweise den DevOps-Workflow mit Docker verbessern möchten, bieten Container besser isolierte Testumgebungen und können Bereitstellungsprobleme lösen, die durch fehlende Abhängigkeiten verursacht werden, wenn Sie in eine Produktionsumgebung wechseln. Wenn Sie eine monolithische Anwendung bereitstellen, ist es in solchen Fällen sinnvoll, Docker- und Windows-Container für die aktuellen .NET Framework-Anwendungen zu verwenden.

In diesem Szenario müssen Sie Ihre vorhandenen Anwendungen in den meisten Fällen nicht zu .NET Core migrieren, sondern können einfach Docker-Container verwenden, die das traditionelle .NET Framework enthalten. Empfohlen wird jedoch, .NET Core zu verwenden, wenn Sie eine vorhandene Anwendung erweitern möchten, z.B. durch Schreiben eines neuen Diensts in ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Verwenden von .NET-Bibliotheken von Drittanbietern oder NuGet-Paketen, die für .NET Core nicht verfügbar sind

[.NET Standard](../../../standard/net-standard.md) kommt in Drittanbieterbibliotheken immer häufiger zum Einsatz und ermöglicht die Codefreigabe in allen .NET-Varianten, einschließlich .NET Core. Mit .NET-Standard 2.0 und höher ist die API-Schnittstellenkompatibilität zwischen verschiedenen Frameworks deutlich größer geworden. Darüber hinaus können .NET Core 2.x- und neuere Anwendungen auch direkt auf vorhandene .NET Framework-Bibliotheken verweisen (weitere Informationen finden Sie unter [.NET Framework 4.6.1-Unterstützung von .NET Standard 2.0](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#net-framework-461-supporting-net-standard-20)).

Zudem erweitert das [Windows Compatibility Pack](../../../core/porting/windows-compat-pack.md) die unter Windows für .NET Standard 2.0 verfügbare API-Oberfläche. Mit diesem Paket kann der größte Teil des vorhandenen Codes mit nur geringen oder ganz ohne Änderungen für .NET Standard 2.x neu kompiliert und unter Windows ausgeführt werden.

Selbst bei diesen außergewöhnlichen Fortschritten seit .NET Standard 2.0 und .NET Core 2.1 können jedoch weiterhin Fälle auftreten, in denen bestimmte NuGet-Pakete nicht ohne Windows ausgeführt werden können und .NET Core nicht unterstützen. Wenn diese Pakete von entscheidender Bedeutung für die Anwendung sind, müssen Sie .NET Framework in Windows-Containern verwenden.

## <a name="using-net-technologies-not-available-for-net-core"></a>Verwenden von .NET-Technologien, die für .NET Core nicht verfügbar sind

Einige .NET Framework-Technologien sind nicht in der aktuellen Version von .NET Core verfügbar (Version 3.1 bei Redaktionsschluss). Einige davon werden möglicherweise in späteren Versionen verfügbar sein, aber andere passen nicht zu den neuen Anwendungsmustern für .NET Core und werden möglicherweise gar nicht verfügbar sein.

In der folgenden Liste ist der Großteil der Technologien aufgeführt, die in .NET Core 3.1 nicht verfügbar sind:

- ASP.NET Web Forms: Diese Technologie ist nur in .NET Framework verfügbar. Eine Integration von ASP.NET Web Forms in .NET Core ist zurzeit nicht geplant.

- WCF-Dienste: Auch wenn eine [WCF-Clientbibliothek](https://github.com/dotnet/wcf) für die Nutzung durch WCF-Dienste von .NET Core verfügbar ist, ist die WCF-Serverimplementierung seit Februar 2020 nur in .NET Framework verfügbar. Dieses Szenario kann für zukünftige Versionen von .NET Core eine Rolle spielen, es gibt sogar Erwägungen, bestimmte APIs in das [Windows Compatibility Pack](../../../core/porting/windows-compat-pack.md) aufzunehmen.

- Workflow-bezogene Dienste: Windows Workflow Foundation (WF), die Workflow-Dienste (WCF + WF in einem einzigen Dienst) und WCF Data Services (früher ADO.NET Data Services) sind nur in .NET Framework verfügbar. Es ist zurzeit nicht vorgesehen, sie in .NET Core zu integrieren.

Zusätzlich zu den in der offiziellen [Roadmap für .NET Core](https://github.com/dotnet/core/blob/master/roadmap.md) aufgeführten Technologien werden möglicherweise andere Features zu .NET Core oder zur neuen [vereinheitlichten .NET-Plattform](https://devblogs.microsoft.com/dotnet/introducing-net-5/) portiert. Sie können erwägen, sich an den Diskussionen auf GitHub zu beteiligen, um Ihre Meinung zu äußern. Wenn Ihrer Ansicht nach noch etwas fehlt, können Sie dies im GitHub-Repository [dotnet/runtime](https://github.com/dotnet/runtime/issues/new) melden.

## <a name="using-a-platform-or-api-that-doesnt-support-net-core"></a>Verwenden einer Plattform oder API ohne Unterstützung von .NET Core

Einige Plattformen von Microsoft und Drittanbietern unterstützen .NET Core nicht. Einige Azure-Dienste stellen beispielsweise ein SDK bereit, das noch nicht für die Nutzung in .NET Core verfügbar ist. Die meisten Azure SDKs sollten irgendwann zu .NET Core/Standard portiert werden, aber einige könnten aus verschiedenen Gründen nicht portiert werden. Sie können die verfügbaren Azure SDKs auf der Seite [Azure SDK Latest Releases](https://azure.github.io/azure-sdk/releases/latest/index.html) (Neueste Azure SDK-Versionen) einsehen.

Wenn eine der Plattformen oder einer der Dienste in Azure .NET Core weiterhin nicht mit der Client-API unterstützt, können Sie in der Zwischenzeit die entsprechende REST-API aus dem Azure-Dienst oder das Client SDK in .NET Framework verwenden.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Leitfaden für .NET Core** \
  [https://docs.microsoft.com/dotnet/core/index](../../../core/index.yml)

- **Porting from .NET Framework to .NET Core (Portieren von .NET Framework zu .NET Core)**  \
  [https://docs.microsoft.com/dotnet/core/porting/index](../../../core/porting/index.md)

- **Einführung zu .NET und Docker** \
  [https://docs.microsoft.com/dotnet/core/docker/introduction](../../../core/docker/introduction.md)

- **.NET-Komponenten – Übersicht** \
  [https://docs.microsoft.com/dotnet/standard/components](../../../standard/components.md)

>[!div class="step-by-step"]
>[Zurück](net-core-container-scenarios.md)
>[Weiter](container-framework-choice-factors.md)
