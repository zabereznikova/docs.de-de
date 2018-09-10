---
title: Erstellen einer zusammengesetzten Benutzeroberfläche auf der Grundlage von Microservices, wobei das Layout der Benutzeroberfläche wiederum von mehreren Microservices generiert wurde
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Erstellen einer zusammengesetzten Benutzeroberfläche auf der Grundlage von Microservices, wobei das Layout der Benutzeroberfläche wiederum von mehreren Microservices generiert wurde
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 79b63c376d25725b2bcb6c16cdb4d06e107d5c07
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44189487"
---
# <a name="creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices"></a>Erstellen einer zusammengesetzten Benutzeroberfläche auf der Grundlage von Microservices, wobei das Layout der Benutzeroberfläche wiederum von mehreren Microservices generiert wurde

Das Fundament einer Microservicesarchitektur ist die serverseitige Verarbeitung von Daten und Logik. Sie können jedoch auch die Benutzeroberfläche Ihrer Anwendung mit Microservices entwerfen. Dies wird als „zusammengesetzte Benutzeroberfläche“ bezeichnet, da sie von Microservices erzeugt wird, statt dass eine monolithische Client-App einfach die Microservices auf dem Server nutzt. Bei diesem Ansatz können die von Ihnen erstellten Microservices sowohl durch Logik als auch durch die visuelle Darstellung ergänzt werden.

In Abbildung 4-20 wird das einfachere Modell dargestellt, in dem eine monolithische Clientanwendung Microservices nutzt. Natürlich kann ein ASP.NET MVC-Dienst zwischengeschaltet werden, der den HTML- und JavaScript-Code erzeugt. In der Darstellung wird vereinfacht dargestellt, wie ein einzelner (monolithischer) Client Microservices nutzt, die nur für die Logik und die Daten zuständig sind, nicht die Benutzeroberfläche (HTML und JavaScript).

![](./media/image20.png)

**Abbildung 4-20:** Eine monolithische Benutzeroberflächenanwendung, die Back-End-Microservices nutzt

Eine zusammengesetzte Benutzeroberfläche hingegen wird von den Microservices selbst erzeugt. Einige der Microservices erzeugen das Layout bestimmter Bereiche der Benutzeroberfläche. Der Hauptunterschied besteht darin, dass die Komponenten der Clientbenutzeroberfläche (z.B. TS-Klassen) auf Vorlagen basieren und dass das Daten strukturierende ViewModel der Benutzeroberfläche für diese Vorlagen aus den einzelnen Microservices stammt.

Zur Startzeit der Clientanwendung registrieren sich alle Komponenten der Clientbenutzeroberfläche (z.B. TypeScript-Klassen) selbst bei einem Infrastrukturmicroservice, der ViewModels für ein bestimmtes Szenario bereitstellen kann. Wenn der Microservice die Form ändert, wird die Benutzeroberfläche automatisch angepasst.

In Abbildung 4-21 wird ein Beispiel für den Ansatz der zusammengesetzten Benutzeroberfläche gezeigt. Die Darstellung ist natürlich vereinfacht, da auch andere Microservices vorhanden sein können, die je nach Verfahren wichtige Aufgaben erledigen. Das kommt darauf an, ob Sie einen herkömmlichen Webansatz (ASP.NET MVC) verwenden oder eine Single-Page-Webanwendung (SPA) erstellen.

![](./media/image21.png)

**Abbildung 4-21:** Beispiel einer Anwendung mit zusammengesetzter Benutzeroberfläche, die von Back-End-Microservices erzeugt wird

Jeder dieser Microservices, die die Benutzeroberfläche erzeugen, ähnelt einem kleinen API-Gateway. In diesem Fall ist jeder jedoch für einen kleinen Bereich der Benutzeroberfläche zuständig.

Eine zusammengesetzte Benutzeroberfläche, die von Microservices erzeugt wird, kann schwieriger oder leichter zu erstellen sein, je nachdem, welche Benutzeroberflächentechnologien Sie verwenden. Die Verfahren für das Erstellen einer herkömmlichen Webanwendung eignen sich z.B. weder zum Erstellen einer SPA oder einer nativen mobilen App, noch zum Entwickeln von Xamarin-Apps, die sehr viel schwieriger für diesen Ansatz genutzt werden können.

Für die Beispielanwendung [eShopOnContainers](https://aka.ms/MicroservicesArchitecture) wird aus verschiedenen Gründen der monolithische Ansatz verwendet. Erstens handelt es sich um eine Einführung in Microservices und Container. Eine zusammengesetzte Benutzeroberfläche ist komplexer, erfordert jedoch auch mehr Komplexität beim Entwerfen und Entwickeln der Benutzeroberfläche. Zweitens stellt eShopOnContainers auch eine native mobile App bereit, die auf Xamarin basiert, die die Komplexität auf der C\#-Clientseite erhöht.

Wir empfehlen Ihnen, sich in den folgenden Ressourcen weiter über die mithilfe von Microservices zusammengesetzte Benutzeroberfläche zu informieren.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Composite UI using ASP.NET (Particular’s Workshop) (Zusammengesetzte Benutzeroberfläche von ASP.NET (Workshop))**
    [*http://go.particular.net/workshop-composite-ui-demo*](http://go.particular.net/workshop-composite-ui-demo)

-   **Ruben Oostinga. The Monolithic Frontend in the Microservices Architecture (Das monolithische Front-End in der Microservices-Architektur)**
    [*http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/*](http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/)

-   **Mauro Servienti. The secret of better UI composition (Das Geheimnis besserer UI-Zusammenstellung)**
    [*https://particular.net/blog/secret-of-better-ui-composition*](https://particular.net/blog/secret-of-better-ui-composition)

-   **Viktor Farcic. Including Front-End Web Components Into Microservices (Einschließen von Front-End-Webkomponenten in Microservices)**
    [*https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/*](https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/)

-   **Managing Frontend in the Microservices Architecture (Verwalten des Front-Ends in der Microservicesarchitektur)**\
    [*https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html*](https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html)


>[!div class="step-by-step"]
[Zurück](microservices-addressability-service-registry.md)
[Weiter](resilient-high-availability-microservices.md)
