---
title: Erstellen einer zusammengesetzten Benutzeroberfläche anhand von Microservices
description: Die Microservicesarchitektur eignet sich nicht nur für das Back-End. Verschaffen Sie sich einen Einblick in der Verwendung für das Front-End.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/20/2018
ms.openlocfilehash: 597927b8eb5463fd3acc651d854404edc24ed96e
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2018
ms.locfileid: "52296476"
---
# <a name="creating-composite-ui-based-on-microservices"></a>Erstellen einer zusammengesetzten Benutzeroberfläche anhand von Microservices

Das Fundament einer Microservicesarchitektur ist die serverseitige Verarbeitung von Daten und Logik. Sie können jedoch auch die Benutzeroberfläche Ihrer Anwendung mit Microservices entwerfen. Dies wird als „zusammengesetzte Benutzeroberfläche“ bezeichnet, da sie von Microservices erzeugt wird, statt dass eine monolithische Client-App einfach die Microservices auf dem Server nutzt. Bei diesem Ansatz können die von Ihnen erstellten Microservices sowohl durch Logik als auch durch die visuelle Darstellung ergänzt werden.

In Abbildung 4-20 wird das einfachere Modell dargestellt, in dem eine monolithische Clientanwendung Microservices nutzt. Natürlich kann ein ASP.NET MVC-Dienst zwischengeschaltet werden, der den HTML- und JavaScript-Code erzeugt. In der Darstellung wird vereinfacht dargestellt, wie ein einzelner (monolithischer) Client Microservices nutzt, die nur für die Logik und die Daten zuständig sind, nicht die Benutzeroberfläche (HTML und JavaScript).

![Eine monolithische Benutzeroberflächenanwendung, die Verbindungen mit individuellen Microservices herstellt.](./media/image20.png)

**Abbildung 4-20:** Eine monolithische Benutzeroberflächenanwendung, die Back-End-Microservices nutzt

Eine zusammengesetzte Benutzeroberfläche hingegen wird von den Microservices selbst erzeugt. Einige der Microservices erzeugen das Layout bestimmter Bereiche der Benutzeroberfläche. Der Hauptunterschied besteht darin, dass die Komponenten der Clientbenutzeroberfläche (z.B. TypeScript-Klassen) auf Vorlagen basieren und dass das Daten strukturierende ViewModel der Benutzeroberfläche für diese Vorlagen aus den einzelnen Microservices stammt.

Zur Startzeit der Clientanwendung registrieren sich alle Komponenten der Clientbenutzeroberfläche (z.B. TypeScript-Klassen) selbst bei einem Infrastrukturmicroservice, der ViewModels für ein bestimmtes Szenario bereitstellen kann. Wenn der Microservice die Form ändert, wird die Benutzeroberfläche automatisch angepasst.

In Abbildung 4-21 wird ein Beispiel für den Ansatz der zusammengesetzten Benutzeroberfläche gezeigt. Diese Darstellung ist vereinfacht, da Sie möglicherweise über andere Microservices verfügen, die je nach Verfahren wichtige Komponenten zusammenführen. Dies hängt davon ab, ob Sie einen herkömmlichen Webansatz (ASP.NET MVC) oder eine SPA (Single-Page-Webanwendung) erstellen.

![In einer Anwendung mit zusammengesetzter Benutzeroberfläche wird jeder Abschnitt der Benutzeroberfläche von einem Microservice generiert, der wie ein kleines Gateway funktioniert.](./media/image21.png)

**Abbildung 4-21:** Beispiel einer Anwendung mit zusammengesetzter Benutzeroberfläche, die von Back-End-Microservices erzeugt wird

Jeder dieser Microservices, die die Benutzeroberfläche erzeugen, ähnelt einem kleinen API-Gateway. In diesem Fall ist jedoch jeder für einen kleinen Bereich der Benutzeroberfläche zuständig.

Eine zusammengesetzte Benutzeroberfläche, die von Microservices erzeugt wird, kann schwieriger oder leichter zu erstellen sein, je nachdem, welche Benutzeroberflächentechnologien Sie verwenden. Beispielsweise verwenden Sie nicht die gleichen Verfahren zum Erstellen einer herkömmlichen Webanwendung, die Sie zum Erstellen einer SPA oder einer nativen, mobilen App verwenden (z.B. beim Entwickeln von Xamarin-Apps, was mit dieser Vorgehensweise viel schwieriger ist).

Für die Beispielanwendung [eShopOnContainers](https://aka.ms/MicroservicesArchitecture) wird aus verschiedenen Gründen der monolithische Ansatz verwendet. Erstens handelt es sich um eine Einführung in Microservices und Container. Eine zusammengesetzte Benutzeroberfläche ist komplexer, erfordert jedoch auch mehr Komplexität beim Entwerfen und Entwickeln der Benutzeroberfläche. Zweitens stellt eShopOnContainers auch eine native mobile App bereit, die auf Xamarin basiert, die die Komplexität auf der C\#-Clientseite erhöht.

Wir empfehlen Ihnen, sich in den folgenden Ressourcen weiter über die mithilfe von Microservices zusammengesetzte Benutzeroberfläche zu informieren.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Composite UI using ASP.NET (Particular’s Workshop) (Zusammengesetzte Benutzeroberfläche mit ASP.NET (Particular-Workshop))** \
  [*https://github.com/Particular/Workshop/tree/master/demos/asp-net-core*](https://github.com/Particular/Workshop/tree/master/demos/asp-net-core)

- **Ruben Oostinga. The Monolithic Frontend in the Microservices Architecture (Das monolithische Front-End in der Microservicesarchitektur)** \
  [*https://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/*](https://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/)

- **Mauro Servienti. The secret of better UI composition (Das Geheimnis besserer Benutzeroberflächenzusammenstellung)** \
  [*https://particular.net/blog/secret-of-better-ui-composition*](https://particular.net/blog/secret-of-better-ui-composition)

- **Viktor Farcic. Including Front-End Web Components Into Microservices (Einschließen von Front-End-Webkomponenten in Microservices)** \
  [*https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/*](https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/)

- **Managing Frontend in the Microservices Architecture (Verwalten des Front-Ends in der Microservicesarchitektur)** \
  [*https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html*](https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html)

>[!div class="step-by-step"]
[Zurück](microservices-addressability-service-registry.md)
[Weiter](resilient-high-availability-microservices.md)