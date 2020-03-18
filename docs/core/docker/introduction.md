---
title: Einführung in Docker
description: Dieser Artikel bietet eine Einführung und einen Überblick über Docker im Rahmen einer.NET Core-Anwendung.
ms.date: 03/20/2019
ms.custom: mvc
ms.openlocfilehash: eedfd1e7c1b361beb9d4f271e739657ef5e894a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157790"
---
# <a name="introduction-to-net-and-docker"></a>Einführung zu .NET und Docker

.NET Core kann problemlos in einem Docker-Container ausgeführt werden. Container bieten eine schlanke Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren, indem sie nur den Kernel gemeinsam nutzen und Ressourcen verwenden, die Ihrer Anwendung zur Verfügung gestellt werden. Wenn Sie mit Docker nicht vertraut sind, wird dringend empfohlen, die [Übersichtsdokumentation](https://docs.docker.com/engine/docker-overview/) von Docker zu lesen.

Weitere Informationen dazu, wie Sie Docker installieren, finden Sie auf der Downloadseite für [Docker Desktop: Community Edition](https://www.docker.com/products/docker-desktop).

## <a name="docker-basics"></a>Docker-Grundlagen

Es gibt einige Konzepte, die Sie kennen sollten. Der Docker-Client verfügt über eine CLI, mit der Sie Images und Container verwalten können. Wie bereits erwähnt, sollten Sie sich die Zeit nehmen, die [Übersichtsdokumentation](https://docs.docker.com/engine/docker-overview/) zu Docker zu lesen.

### <a name="images"></a>Bilder

Ein Image ist eine geordnete Auflistung von Dateisystemänderungen, die die Grundlage für einen Container bilden. Das Image weist keinen Zustand auf und ist schreibgeschützt. Meistens basiert ein Image auf einem anderen Image, allerdings mit einer gewissen Anpassung. Wenn Sie beispielsweise ein neues Image für Ihre Anwendung erstellen, würden Sie als Grundlage ein vorhandenes Image verwenden, das bereits die .NET Core Runtime enthält.

Da Container aus Images erstellt werden, weisen Images eine Reihe von Ausführungsparametern auf (z.B. eine startende ausführbare Datei), die beim Start des Containers ausgeführt werden.

### <a name="containers"></a>Container

Ein Container ist eine ausgeführte Instanz eines Images. Wenn Sie Ihr Image erstellen, stellen Sie Ihre Anwendung und Abhängigkeiten bereit. Anschließend können mehrere Container instanziiert werden, die jeweils voneinander isoliert sind. Jede Containerinstanz verfügt über ein eigenes Dateisystem, eigenen Speicher und eine eigene Netzwerkschnittstelle.

### <a name="registries"></a>Registrierungen

Containerregistrierungen sind eine Sammlung von Imagerepositorys. Sie können Ihre Images auf einem Registrierungsimage basieren. Sie können Container direkt aus einem Image in einer Registrierung erstellen. Die [Beziehung zwischen Docker-Containern, -Images und -Registrys](../../architecture/microservices/container-docker-introduction/docker-containers-images-registries.md) ist ein wichtiges Konzept beim [Entwurf und Aufbau von Containeranwendungen oder Microservices](../../architecture/microservices/architect-microservice-container-applications/index.md). Durch diese Vorgehensweise wird die Zeit zwischen Entwicklung und Bereitstellung deutlich verkürzt.

Docker verfügt über eine öffentliche Registrierung, die auf dem [Docker-Hub](https://hub.docker.com/) gehostet wird, die Sie verwenden können. Images, die sich auf [.NET Core beziehen](https://hub.docker.com/_/microsoft-dotnet-core/), werden auf dem Docker-Hub aufgeführt.

Die Microsoft Container Registry (MCR) ist die offizielle Quelle für von Microsoft bereitgestellte Containerimages. MCR basiert auf Azure CDN, um global replizierte Images bereitzustellen. MCR verfügt jedoch nicht über eine öffentlich zugängliche Website, und der primäre Weg, um mehr über von Microsoft bereitgestellte Containerimages zu erfahren, führt über die [Microsoft Docker-Hubseiten](https://hub.docker.com/_/microsoft-dotnet-core/).

### <a name="dockerfile"></a>Docker-Datei

Eine **Dockerfile-Datei** ist eine Datei, die einen Satz von Anweisungen definiert, mit dem ein Image erstellt wird. Jede Anweisung in der **Dockerfile-Datei** erstellt eine Ebene im Image. Wenn Sie das Image neu erstellen, werden in den meisten Fällen nur die Ebenen neu erstellt, die sich geändert haben. Die **Dockerfile-Datei** kann an andere Benutzer verteilt werden und ermöglicht es ihnen, ein neues Image auf die gleiche Weise zu erstellen, wie Sie es erstellt haben. Dies ermöglicht es Ihnen zwar, die *Anweisungen* zur Erstellung des Images zu verteilen, aber die Hauptmethode zur Verteilung Ihres Images ist die Veröffentlichung in einer Registrierung.

## <a name="net-core-images"></a>.NET Core-Images

Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar. Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.

Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind. So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.

## <a name="azure-services"></a>Azure-Dienste

Verschiedene Azure-Dienste unterstützen Container. Sie erstellen ein Docker-Image für Ihre Anwendung und stellen es für einen der folgenden Dienste bereit:

- [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/)\
Skalieren und orchestrieren Sie Linux-Container mit Kubernetes.

- [Azure App Service](https://azure.microsoft.com/services/app-service/containers/)\
Stellen Sie Web-Apps und APIs mithilfe von Linux-Containern in einer PaaS-Umgebung bereit.

- [Azure Container Instances](https://azure.microsoft.com/services/container-instances/)\
Hosten Sie Ihren Container in der Cloud ohne übergeordnete Verwaltungsdienste.

- [Azure Batch](https://azure.microsoft.com/services/batch/)\
Führen Sie sich wiederholende Computeaufträge mit Containern aus.

- [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)\
Optimieren, verschieben und modernisieren Sie .NET-Anwendungen in Microservices mithilfe von Windows Server-Containern.

- [Azure Container Registry](https://azure.microsoft.com/services/container-registry/)\
Speichern und verwalten Sie Containerimages für alle Typen von Azure-Bereitstellungen.

## <a name="next-steps"></a>Nächste Schritte

- [Bereitstellen einer .NET Core-Anwendung im Container](build-container.md)
- [Bereitstellen einer ASP.NET Core-Anwendung im Container.](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [Tutorial zu ASP.NET Core-Microservices](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [Informationen zu Containertools in Visual Studio](/visualstudio/containers/overview)
