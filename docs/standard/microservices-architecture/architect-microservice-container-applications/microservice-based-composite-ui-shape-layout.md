---
title: "Erstellen von zusammengesetzten UI basierend auf Microservices, einschließlich visual UI-Form und das Layout von mehreren Microservices generiert"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Erstellen von zusammengesetzten UI basierend auf Microservices, einschließlich visual UI-Form und das Layout von mehreren Microservices generiert"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4b32fed5eb0de02b01665efa4368eb83e3fda08d
ms.sourcegitcommit: e99dfadbca1992c187179b6a3b42bef44534ebb6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2017
---
# <a name="creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices"></a>Erstellen von zusammengesetzten UI basierend auf Microservices, einschließlich visual UI-Form und das Layout von mehreren Microservices generiert

Microservices Architektur wird häufig mit der serverseitigen Verarbeitung von Daten und Logik gestartet. Allerdings ist ein komplexeren Ansatz können Sie Ihre Anwendung entwerfen, die ebenfalls Microservices UI anhand. Daraus folgt, mit einer zusammengesetzten Benutzeroberfläche von Microservices, anstatt auf dem Server und nur eine monolithischen Client-app, die Nutzung der Microservices Microservices erzeugt. Bei diesem Ansatz kann die von Ihnen erstelle Microservices mit Logik und die visuelle Darstellung abgeschlossen sein.

Abbildung 4-20 zeigt die einfachere Lösung einfach Microservices von monolithischen Clientanwendungen nutzen. Natürlich, könnten Sie einen ASP.NET MVC-Dienst, BETWEEN, erzeugt der HTML- und JavaScript verfügen. Die Abbildung ist eine Vereinfachung, die hervorgehoben, Sie verfügen über eine einzelne (monolithischen) Client UI nutzen die Microservices, die nur auf Logik und die Daten nicht auf der UI-Form (HTML und JavaScript) zu konzentrieren.

![](./media/image20.png)

**Abbildung 4-20**. Back-End-Microservices Nutzen einer monolithischen UI-Anwendung

Im Gegensatz dazu eine zusammengesetzte Benutzeroberfläche genau generiert und aus, das die Microservices selbst. Einige der Microservices Laufwerk der visuellen Form des bestimmte Bereiche der Benutzeroberfläche. Der Hauptunterschied besteht darin, dass Client UI-Komponenten (TS-Klassen, z. B.) auf Basis der Vorlagen, und die Daten strukturieren UI ViewModel für Vorlagen ergibt sich aus jeder Microservice.

Am Client-Anwendung die Startzeit registriert aller Client-UI-Komponenten (z. B. TypeScript-Klassen) selbst mit einer Infrastruktur Microservice ViewModels für ein bestimmtes Szenario bereitstellen. Wenn die Microservice Form ändert, ändert sich auch die Benutzeroberfläche.

Abbildung 4-21 zeigt eine Version dieses zusammengesetzter UI-Ansatzes. Dies vereinfacht, da Sie möglicherweise andere Microservices haben, die präzise Teile, die basierend auf verschiedenen Verfahren anwendbar sind – Sie davon abhängig, ob Sie einen herkömmlichen Web-Ansatz (ASP.NET MVC) oder ein SPA (einseitigen-Anwendung) erstellen.

![](./media/image21.png)

**Abbildung 4-21**. Beispiel einer zusammengesetzten UI-Anwendung, die vom Back-End-Microservices strukturiert

Jedes dieser Benutzeroberfläche Komposition Microservices wäre ähnlich wie ein kleines-API-Gateway. Aber in diesem Fall ist jede für einen kleinen Benutzeroberflächenbereich zuständig.

Ein zusammengesetzter UI-Ansatz, der durch Microservices gesteuert wird, kann schwieriger sein oder weniger also je nachdem welche UI-Technologien verwenden. Beispielsweise wird können nicht die gleichen Techniken für das Erstellen einer herkömmlichen Web-Anwendung, die Sie zum Erstellen einer SPA oder für systemeigene mobile app verwenden (wie bei der Entwicklung von Xamarin-apps, die schwieriger für diesen Ansatz sein können).

Die [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) beispielanwendung verwendet die monolithischen UI Ansatz für mehrere Gründe geben. Erstens handelt es sich um eine Einführung in die Microservices und Container. Eine zusammengesetzte Benutzeroberfläche ist komplexer erfordert jedoch auch weiteren Komplexität beim Entwerfen und Entwickeln der Benutzeroberflächenautomatisierungs. Zweitens stellt eShopOnContainers auch eine systemeigene mobile app, die basierend auf der Xamarin, die sie auf dem Client C komplexer machen würden\# Side.

Allerdings empfehlen wir Ihnen, die folgenden Verweise zu verwenden, um weitere Informationen zu zusammengesetzte Microservices UI abhängig.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Zusammengesetzte Benutzeroberfläche mithilfe von ASP.NET (insbesondere der Workshop)**
    [*http://go.particular.net/workshop-composite-ui-demo*](http://go.particular.net/workshop-composite-ui-demo)

-   **Ruben Oostinga. Das monolithischen Front-End in der Architektur des Microservices**
    [*http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/*](http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/)

-   **Mauro Servienti. Der geheime Schlüssel des besser UI Komposition**
    [*https://particular.net/blog/secret-of-better-ui-composition*](https://particular.net/blog/secret-of-better-ui-composition)

-   **Viktor Farcic. -Front-End-Webkomponenten in Microservices einschließlich**
    [*https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/*](https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/)

-   **Verwalten von Front-End in der Microservices-Architektur**\
    [*http://Allegro.Tech/2016/03/Managing-Frontend-in-the-microservices-Architecture.HTML*](http://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html)


>[!div class="step-by-step"]
[Vorherigen] (Microservices-Adressierbarkeit-Service-registry.md) [weiter] (robusten-High-Availability-microservices.md)
