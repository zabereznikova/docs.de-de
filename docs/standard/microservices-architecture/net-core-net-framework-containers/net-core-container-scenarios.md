---
title: "Beim Auswählen von .NET Core für Docker-Containern"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Beim Auswählen von .NET Core für Docker-Containern"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b7e2322bab7937c41d4659fefef11c8937d5eae7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-core-for-docker-containers"></a>Beim Auswählen von .NET Core für Docker-Containern

Die Modularität und der Lightweight-Charakter .NET Core ist es perfekt für Container. Beim Bereitstellen und starten Sie einen Container ist seines Abbilds wesentlich kleiner mit .NET Core als mit .NET Framework. Im Gegensatz dazu für die Verwendung der .NET Framework für einen Container muss des Abbilds auf dem Windows Server Core-Image basieren also viel größere als die Windows Nano Server oder Linux-Images, die Sie für .NET Core verwenden.

Darüber hinaus ist .NET Core plattformübergreifende, sodass Sie Server-apps mit Linux- oder Windows-containerimages bereitstellen können. Wenn Sie herkömmliche .NET Framework verwenden, können Sie Bilder, die basierend auf Windows Server Core nur bereitstellen.

Im folgenden finden eine ausführlichere Erläuterung der Gründe für das .NET Core auswählen.

## <a name="developing-and-deploying-cross-platform"></a>Entwickeln und Bereitstellen von plattformübergreifende

Es ist offensichtlich, wenn Ihr Ziel ist, haben ist eine Anwendung (Web-Anwendung oder Dienst), die auf mehreren Plattformen von Docker (Linux und Windows) unterstützt die richtige Wahl ausführen können .NET Core, da .NET Framework nur Windows unterstützt.

Außerdem unterstützt .NET Core MacOS als eine Entwicklungsplattform. Wenn Sie Container mit Docker-Host bereitstellen, muss jedoch diesem Host (derzeit) unter Linux oder Windows basieren. Beispielsweise können in einer Entwicklungsumgebung Sie eine Linux-VM auf einem Macintosh-Computer ausgeführt verwenden

[Visual Studio](https://www.visualstudio.com/) bietet eine integrierte Entwicklungsumgebung (IDE) für Windows und Docker-Entwicklung unterstützt. 

[Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/) ist eine IDE, die Entwicklung von Xamarin Studio, MacOS auf und Docker seit Mitte 2017 unterstützt.

Sie können auch [Visual Studio Code](https://code.visualstudio.com/) (Visual Studio-Code) auf MacOS, Linux und Windows. .NET Core, einschließlich IntelliSense und debugging wird von Visual Studio Code vollständig unterstützt. Da Visual Studio Code-Editor für eine einfache ist, können Sie sie zum Entwickeln von Datenvolumes apps auf dem Mac in Verbindung mit der Docker-Befehlszeilenschnittstelle und den [.NET Core-Befehlszeilenschnittstelle (CLI) Tools](https://docs.microsoft.com/dotnet/core/tools/?tabs=netcore2x). Sie können die .NET Core auch abzielen, die meisten Drittanbieter-Editoren wie Sublime Text, Emacs vi und der Open Source-OmniSharp-Projekts, die IntelliSense-Unterstützung für .NET-Sprachen bereitstellt. Zusätzlich zu den IDEs und Editoren können Sie die .NET Core-CLI für alle unterstützten Plattformen verwenden.

## <a name="using-containers-for-new-green-field-projects"></a>Mithilfe von Containern für neue Projekte für ("Grün-Field")

Container werden häufig in Verbindung mit einer Architektur Microservices verwendet, obwohl sie auch verwendet werden können, um containerize Web-apps oder Dienste, die jede architektonische Muster folgen. Können Sie .NET Framework auf Windows-Container, aber aufgrund der Modularität und einfache Charakter .NET Core ist es perfekt für Container und Microservices Architekturen. Beim Erstellen und ein Containers bereitstellen ist seines Abbilds wesentlich kleiner mit .NET Core als mit .NET Framework.

## <a name="creating-and-deploying-microservices-on-containers"></a>Erstellen und Bereitstellen von Microservices für Container

Herkömmliche .NET Framework können Sie zum Erstellen von Microservices-basierte Anwendungen (ohne Container) mithilfe von einfachen Prozessen. Auf diese Weise daran, dass .NET Framework bereits installiert und von mehreren Prozessen gemeinsam Prozesse sind hell und schnellen starten. Allerdings bei Verwendung von Containern des Abbilds für herkömmliche .NET Framework basiert auch auf Windows Server Core und stellt es zu hoher Microservices auf Container vor.

Im Gegensatz dazu ist .NET Core die besten Kandidaten aus, wenn Sie ein Microservices dienstorientierten System, das basierend auf den Container, Hinwendung, da .NET Core einfache ist. Darüber hinaus sind die verwandte containerimages, die Linux-Image oder das Bild Windows Nano lean und kleine Container Licht herstellen und schnell zu starten.

Ein Microservice soll so klein wie möglich sein: hell sein, wenn oben rotiert, um einen geringen Ressourcenbedarf, haben Sie eine kleine begrenzt, die den Kontext zu einen kleinen Bereich von Anliegen darstellen, und klicken Sie in der Lage zu starten und beenden Sie schnell haben. Für diese Anforderungen sollten Sie klein und Fast instanziieren containerimages wie die .NET Core-containerimages zu verwenden.

Eine Architektur Microservices ermöglicht außerdem Technologien über Dienstgrenzen hinweg mischen. Dies ermöglicht eine stufenweise Migration zu .NET Core für neue Microservices, die Arbeit in Verbindung mit anderen Microservices oder Dienste, die mit Node.js, Python, Java, GoLang oder anderen Technologien entwickelt wurde.

## <a name="deploying-high-density-in-scalable-systems"></a>Bereitstellen von hoher Dichte im skalierbarer Systeme

Wenn das Container-basierten System die beste mögliche Dichte Granularität und Leistung benötigt, sind .NET Core und ASP.NET Core der besten Optionen. ASP.NET Core ist bis zu zehnmal schneller als in herkömmlichen .NET Framework, ASP.NET und es anderen gängigen Technologien für Microservices, z. B. Java Servlets Go und Node.js führt.

Dies ist besonders relevant für Microservices Architekturen, dort stehen Ihnen Hunderte von Microservices (Container) ausführen können. Mit ASP.NET Core Bildern (basierend auf der .NET Core-Laufzeit) unter Linux oder Windows Nano können Sie Ihr System eine wesentlich geringere Anzahl von Servern oder virtuellen Computern, letztlich Kosten in Infrastruktur speichern und Hosten von ausführen.


>[!div class="step-by-step"]
[Vorherigen] (Allgemeine-guidance.md) [weiter] (Net-Framework-Container-scenarios.md)
