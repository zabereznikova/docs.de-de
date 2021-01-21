---
title: Wann sollte .NET Framework für Docker-Container verwendet werden?
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Wann sollte .NET Framework für Docker-Container verwendet werden?
ms.date: 01/13/2021
ms.openlocfilehash: 476f891a70a220172f84d8168c8492416b8e56bd
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188114"
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Wann sollte .NET Framework für Docker-Container verwendet werden?

Während .NET 5 erhebliche Vorteile für neue Anwendungen und Anwendungsmuster bietet, ist .NET Framework nach wie vor eine gute Wahl für viele bestehende Szenarios.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Direktes Migrieren vorhandener Anwendungen zu einem Windows Server-Container

Mithilfe von Docker-Containern können Sie die Bereitstellung vereinfachen, auch wenn Sie keine Microservices erstellen. Wenn Sie beispielsweise den DevOps-Workflow mit Docker verbessern möchten, bieten Container besser isolierte Testumgebungen und können Bereitstellungsprobleme lösen, die durch fehlende Abhängigkeiten verursacht werden, wenn Sie in eine Produktionsumgebung wechseln. Wenn Sie eine monolithische Anwendung bereitstellen, ist es in solchen Fällen sinnvoll, Docker- und Windows-Container für die aktuellen .NET Framework-Anwendungen zu verwenden.

In diesem Szenario müssen Sie Ihre vorhandenen Anwendungen in den meisten Fällen nicht zu .NET 5 migrieren, sondern können einfach Docker-Container verwenden, die das traditionelle .NET Framework enthalten. Empfohlen wird jedoch, .NET 5 zu verwenden, wenn Sie eine vorhandene Anwendung erweitern möchten, z. B. durch Schreiben eines neuen Diensts in ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-5"></a>Verwenden von nicht für .NET 5 verfügbaren .NET-Bibliotheken von Drittanbietern oder NuGet-Paketen

[.NET Standard](../../../standard/net-standard.md) kommt in Drittanbieterbibliotheken immer häufiger zum Einsatz und ermöglicht die Codefreigabe in allen .NET-Varianten, einschließlich .NET 5. Mit .NET-Standard 2.0 und höher ist die API-Schnittstellenkompatibilität zwischen verschiedenen Frameworks deutlich größer geworden. Darüber hinaus können .NET Core 2.x- und neuere Anwendungen auch direkt auf vorhandene .NET Framework-Bibliotheken verweisen (weitere Informationen finden Sie unter [.NET Framework 4.6.1-Unterstützung von .NET Standard 2.0](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#net-framework-461-supporting-net-standard-20)).

Zudem erweitert das [Windows Compatibility Pack](../../../core/porting/windows-compat-pack.md) die unter Windows für .NET Standard 2.0 verfügbare API-Oberfläche. Mit diesem Paket kann der größte Teil des vorhandenen Codes mit nur geringen oder ganz ohne Änderungen für .NET Standard 2.x neu kompiliert und unter Windows ausgeführt werden.

Trotz dieser außergewöhnlichen Fortschritte seit .NET Standard 2.0 und .NET Core 2.1 und höher können jedoch weiterhin Fälle auftreten, in denen bestimmte NuGet-Pakete nicht ohne Windows ausgeführt werden können und .NET Core und höher nicht unterstützen. Wenn diese Pakete von entscheidender Bedeutung für die Anwendung sind, müssen Sie .NET Framework in Windows-Containern verwenden.

## <a name="using-net-technologies-not-available-for-net-5"></a>Verwenden von nicht für .NET 5 verfügbaren .NET-Technologien

Einige .NET Framework-Technologien sind nicht in der aktuellen Version von .NET verfügbar (Version 5.0 bei Redaktionsschluss). Einige davon werden möglicherweise in späteren Versionen verfügbar sein, aber andere passen nicht zu den neuen Anwendungsmustern für .NET Core und werden möglicherweise gar nicht verfügbar sein.

In der folgenden Liste ist der Großteil der Technologien aufgeführt, die in .NET 5 nicht verfügbar sind:

- ASP.NET Web Forms: Diese Technologie ist nur in .NET Framework verfügbar. Eine Integration von ASP.NET Web Forms in .NET 5 und höher ist zurzeit nicht geplant.

- WCF-Dienste: Auch wenn eine [WCF-Clientbibliothek](https://github.com/dotnet/wcf) für die Nutzung von WCF-Diensten mit .NET 5 verfügbar ist, ist die WCF-Serverimplementierung nur im .NET Framework verfügbar (Stand: Januar 2021).

- Workflow-bezogene Dienste: Windows Workflow Foundation (WF), die Workflow-Dienste (WCF + WF in einem einzigen Dienst) und WCF Data Services (früher ADO.NET Data Services) sind nur in .NET Framework verfügbar. Es ist zurzeit nicht vorgesehen, diese in .NET 5 zu integrieren.

Zusätzlich zu den in der offiziellen [Roadmap für .NET](https://github.com/dotnet/core/blob/master/roadmap.md) aufgeführten Technologien werden möglicherweise andere Features zur neuen [vereinheitlichten .NET-Plattform](https://devblogs.microsoft.com/dotnet/introducing-net-5/) portiert. Sie können erwägen, sich an den Diskussionen auf GitHub zu beteiligen, um Ihre Meinung zu äußern. Wenn Ihrer Ansicht nach noch etwas fehlt, können Sie dies im GitHub-Repository [dotnet/runtime](https://github.com/dotnet/runtime/issues/new) melden.

## <a name="using-a-platform-or-api-that-doesnt-support-net-5"></a>Verwenden einer Plattform oder API ohne Unterstützung für .NET 5

Einige Plattformen von Microsoft und Drittanbietern unterstützen .NET 5 nicht. Einige Azure-Dienste stellen beispielsweise ein SDK bereit, das noch nicht in .NET 5 genutzt werden kann. Die meisten Azure SDKs sollten irgendwann zu .NET 5 bzw. .NET Standard portiert werden, aber bei einigen könnten das aus verschiedenen Gründen nicht möglich sein. Sie können die verfügbaren Azure SDKs auf der Seite [Azure SDK Latest Releases](https://azure.github.io/azure-sdk/releases/latest/index.html) (Neueste Azure SDK-Versionen) einsehen.

Wenn eine der Plattformen oder einer der Dienste in Azure .NET 5 weiterhin nicht mit der Client-API unterstützt, können Sie in der Zwischenzeit die entsprechende REST-API des Azure-Diensts oder das Client SDK des .NET Framework verwenden.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **.NET-Grundlagen** \
  [https://docs.microsoft.com/dotnet/fundamentals](../../../fundamentals/index.yml)

- **Portieren von Projekten zu .NET 5** \
  [https://channel9.msdn.com/Events/dotnetConf/2020/Porting-Projects-to-NET-5](https://channel9.msdn.com/Events/dotnetConf/2020/Porting-Projects-to-NET-5)

- **Leitfaden zu .NET in Docker** \
  [https://docs.microsoft.com/dotnet/core/docker/introduction](../../../core/docker/introduction.md)

- **.NET-Komponenten – Übersicht** \
  [https://docs.microsoft.com/dotnet/standard/components](../../../standard/components.md)

>[!div class="step-by-step"]
>[Zurück](net-core-container-scenarios.md)
>[Weiter](container-framework-choice-factors.md)
