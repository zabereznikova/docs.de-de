---
title: Wann sollte .NET Core für Docker-Container verwendet werden?
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Wann sollte .NET Core für Docker-Container verwendet werden?
ms.date: 01/30/2020
ms.openlocfilehash: b3cb1eefe739b4ffdbbdd0bdcb3c74b51862704b
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77501850"
---
# <a name="when-to-choose-net-core-for-docker-containers"></a>Wann sollte .NET Core für Docker-Container verwendet werden?

Die Modularität und der schlanke Aufbau von .NET Core macht es perfekt für Container. Das Image eines mit .NET Core bereitgestellten und ausgeführten Containers ist wesentlich kleiner als bei .NET Framework. Um .NET Framework für einen Container verwenden zu können, muss das Image auf dem Windows Server Core-Image basieren, das viel größer ist als die Windows Nano Server- oder Linux-Images, die für .NET Core verwendet werden.

Darüber hinaus funktioniert .NET Core plattformübergreifend, sodass Sie Server-Apps mit Linux- oder Windows-Containerimages bereitstellen können. Wenn Sie jedoch das herkömmliche .NET Framework verwenden, können Sie nur auf Windows Server Core basierende Images bereitstellen.

Im Folgenden finden Sie eine ausführlichere Erläuterung der Vorteile von .NET Core.

## <a name="developing-and-deploying-cross-platform"></a>Plattformübergreifendes Entwickeln und Bereitstellen

Wenn Sie eine Anwendung (Webanwendung oder Dienst) entwickeln möchten, die auf mehreren von Docker unterstützten Plattformen (Linux und Windows) ausgeführt werden kann, ist .NET Core die richtige Wahl, da .NET Framework nur Windows unterstützt.

.NET Core unterstützt auch macOS als Entwicklungsplattform. Wenn Sie Container jedoch auf einem Docker-Host bereitstellen, muss der Host (aktuell) auf Linux oder Windows basieren. In einer Entwicklungsumgebung können Sie z.B. eine Linux-VM benutzen, die auf einem Mac ausgeführt wird.

[Visual Studio](https://www.visualstudio.com/vs/) stellt eine integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) für Windows und Mac bereit und unterstützt die Entwicklung auf Docker.

[Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/) ist eine IDE, eine Weiterentwicklung von Xamarin Studio, die unter macOS ausgeführt wird und die Docker-basierte Anwendungsentwicklung unterstützt. Dies sollte die bevorzugte Wahl für Entwickler sein, die auf Mac-Computern arbeiten und eine leistungsfähige IDE verwenden möchten.

Sie können außerdem [Visual Studio Code](https://code.visualstudio.com/) unter macOS, Linux und Windows verwenden. Visual Studio Code bietet vollständige Unterstützung für .NET Core, einschließlich IntelliSense und Debugging. Mit dem schlanken Editor in Visual Studio Code können Sie Container-Apps auf dem Mac entwickeln und dazu auch die Docker-CLI und die [.NET Core-CLI](../../../core/tools/index.md) nutzen. Sie können außerdem mit den meisten Drittanbieter-Editoren für .NET Core entwickeln, z.B. mit Sublime, Emacs oder vi sowie auch mit den Tools des Open Source-Projekts „Omnisharp“, das darüber hinaus IntelliSense-Unterstützung bereitstellt.

Zusätzlich zu den IDEs und Editoren können Sie die [.NET Core-CLI](../../../core/tools/index.md) für alle unterstützten Plattformen verwenden.

## <a name="using-containers-for-new-green-field-projects"></a>Verwenden von Containern für neue Projekte (Greenfield-Projekte)

Container werden meist in Verbindung mit einer Microservicearchitektur eingesetzt, obwohl sie auch für Web-Apps oder Dienste mit jedem beliebigen Architekturmuster verwendet werden können. .NET Framework lässt sich auch für Windows-Container verwenden, allerdings eignet sich .NET Core durch die Modularität und den einfachen Aufbau ideal für Container und Microservicesarchitekturen. Das Image eines mit .NET Core erstellten und bereitgestellten Containers ist wesentlich kleiner als bei .NET Framework.

## <a name="create-and-deploy-microservices-on-containers"></a>Erstellen und Bereitstellen von Microservices in Containern

Auf Microservices basierende Anwendungen (ohne Container) lassen sich mithilfe des traditionellen .NET Framework erstellen, indem Sie einfache Prozesse verwenden. Da .NET Framework bereits installiert und von allen Prozesse genutzt wird, sind die Prozesse schnell und einfach zu starten. Wenn Sie jedoch Container verwenden, basiert auch das Image für das traditionelle .NET Framework auf Windows Server Core. Aus diesem Grund ist es zu groß für die Bereitstellung von Microservices in Containern. Teams haben jedoch auch nach Möglichkeiten gesucht, um die Erfahrung für .NET Framework-Benutzer zu verbessern. Kürzlich wurde die Größe der [Windows Server Core-Containerimages um mehr als 40 % verkleinert](https://devblogs.microsoft.com/dotnet/we-made-windows-server-core-container-images-40-smaller). 

.NET Core ist hingegen die beste Wahl, wenn Sie ein an Microservices orientiertes System erstellen, das auf Containern basiert, weil .NET Core schlank ist. Außerdem sind die dazugehörigen Containerimages für entweder Linux oder Windows Nano Server schlank und klein, sodass sich Container leicht und schnell starten lassen.

Ein Microservice soll so klein wie möglich sein: schlank beim Hochfahren, mit einem kleinen Fußabdruck und engen Kontextgrenzen (siehe dazu DDD, [Domain-Driven Design](https://en.wikipedia.org/wiki/Domain-driven_design)), mit der Darstellung eines kleinen Sachbereichs und der Fähigkeit, schnell gestartet und beendet zu werden. Um diese Anforderungen zu erfüllen, sollten Sie kleine und schnell zu instanziierende Containerimages wie das .NET Core-Containerimage verwenden.

Durch eine Microservicearchitektur ist also eine dienstübergreifende Kombination aus Technologien möglich. Dies ermöglicht eine kontinuierliche Migration zu .NET Core für neue Microservices, die mit anderen Microservices oder Diensten zusammenarbeiten, die mit Node.js, Python, Java, GoLang oder anderen Technologien entwickelt wurden.

## <a name="deploying-high-density-in-scalable-systems"></a>Bereitstellen von hoher Dichte in skalierbaren Systemen

Wenn Sie für Ihr containerbasiertes System die bestmögliche Dichte, Granularität und Leistung benötigen, sind .NET Core und ASP.NET Core die besten Optionen für Sie. ASP.NET Core ist zehnmal schneller als ASP.NET im herkömmlichen .NET Framework und steht im Vergleich zu anderen bekannten Branchentechnologien für Microservices, wie Java Servlets, Go und Node.js, an der Spitze.

Dies betrifft insbesondere Microservicearchitekturen, in denen Hunderte von Microservices (Container) ausgeführt werden können. Mit ASP.NET Core-Images unter Linux oder Windows Nano, die auf der .NET Core-Runtime basieren, können Sie Ihr System mit einer wesentlich geringeren Anzahl von Servern oder virtuellen Computern ausführen und so Kosten für Infrastruktur und das Hosting sparen.

>[!div class="step-by-step"]
>[Zurück](general-guidance.md)
>[Weiter](net-framework-container-scenarios.md)
