---
title: Eine Einführung in blazor für ASP.net Web Forms-Entwicklern
description: Eine Einführung in blazor und das Schreiben von voll Stapel-Web-Apps mit .net
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 6c045cd9c4378bd19f97dd722db054c969491d0b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841930"
---
# <a name="an-introduction-to-blazor-for-aspnet-web-forms-developers"></a>Eine Einführung in blazor für ASP.net Web Forms-Entwicklern

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Das ASP.net-Web Forms Framework war eine Grundvoraussetzung für die .net-Webentwicklung seit dem ersten .NET Framework in 2002. Wenn sich das Web immer noch in seiner Kindheit befand, haben ASP.net Web Forms die einfache und produktive Erstellung von Web-Apps erleichtert, indem viele der Muster übernommen wurden, die für die Desktop Entwicklung verwendet wurden. In ASP.net Web Forms können Webseiten schnell aus wiederverwendbaren UI-Steuerelementen zusammengesetzt werden. Benutzerinteraktionen werden auf natürliche Weise als Ereignisse behandelt. Es gibt ein umfassendes Ökosystem von Web Forms UI-Steuerelementen, die von Microsoft-und Steuerungs Anbietern bereitgestellt werden. Die-Steuerelemente erleichtern das Herstellen von Verbindungen mit Datenquellen und das Anzeigen von umfangreichen Datenvisualisierungen. Beim visuellen Element stellt der Web Forms-Designer eine einfache Drag & Drop-Schnittstelle zum Verwalten von Steuerelementen bereit.

Im Laufe der Jahre hat Microsoft neue ASP.NET-basierte Webframe Works eingeführt, um Webentwicklungs Trends zu beheben. Zu den Webframe Works gehören ASP.NET MVC, ASP.net Web Pages und vor kurzem ASP.net Core. Bei jedem neuen Framework haben einige den bevorstehenden ablehnen von ASP.net-Web Forms vorhergesagt und als veraltetes, ausgemutetes Webframework kritisiert. Trotz dieser Vorhersagen finden viele .NET-Webentwickler weiterhin ASP.net Web Forms eine einfache, stabile und produktive Methode, um Ihre Arbeit zu erledigen.

Zum Zeitpunkt der Erstellung der Erstellung verwenden fast die Hälfte einer Million Webentwickler ASP.net Web Forms jeden Monat. Das ASP.net-Web Forms Framework ist so stabil, dass Dokumente, Beispiele, Bücher und Blogbeiträge aus einem Jahrzehnt vor einem Jahrzehnt nützlich und relevant bleiben. Bei vielen .NET-Webentwicklern ist "ASP.net" immer noch mit "ASP.net Web Forms" zu tun, wie es bei der ersten Konzeption von .net der Fall war. Argumente für die vor-und Nachteile der ASP.net-Web Forms im Vergleich zu den anderen neuen .net-Webframe Works können bei auftreten. ASP.net Web Forms ist ein beliebtes Framework zum Erstellen von Web-Apps.

Sogar so werden Innovationen bei der Softwareentwicklung nicht verlangsamt. Alle Softwareentwickler müssen auf dem neuesten Stand der neuen Technologien und Trends bleiben. Vor allem sind zwei Trends zu berücksichtigen:

1. Die Umstellung auf Open Source und plattformübergreifend
2. Die Umstellung der APP-Logik auf den Client

## <a name="an-open-source-and-cross-platform-net"></a>Ein Open Source-und plattformübergreifendes .net

Als .net und Web Forms ASP.net zuerst ausgeliefert wurden, hat sich das Platform-Ökosystem viel anders als heute gesehen. Die Desktop-und Server Märkte waren von Windows dominiert. Alternative Plattformen wie macOS und Linux haben immer noch Schwierigkeiten, eine Traktion zu gewinnen. ASP.net Web Forms ist mit der .NET Framework als nur-Windows-Komponente ausgeliefert und Web Forms ASP.net-apps können nur auf Windows Server-Computern ausgeführt werden. Viele moderne Umgebungen verwenden jetzt verschiedene Plattformen für Server und Entwicklungs Computer, sodass die plattformübergreifende Unterstützung für viele Benutzer eine absolute Voraussetzung ist.

Die meisten modernen Webframe Works sind nun auch Open-Source-Funktionen, die eine Reihe von Vorteilen haben. Benutzer sind nicht für einen einzelnen Projektbesitzer verpflichtet, um Fehler zu beheben und Features hinzuzufügen. Open-Source-Projekte bieten eine verbesserte Transparenz für den Entwicklungsfortschritt und anstehende Änderungen. Open-Source-Projekte profitieren von Beiträgen aus einer ganzen Community und fördern ein unterstützendes Open Source-Ökosystem. Trotz der Risiken von Open Source haben viele Consumer und Mitwirkende geeignete entschärfungen gefunden, mit denen Sie die Vorteile eines Open Source-Ökosystems auf sichere und sinnvolle Weise nutzen können. Beispiele für derartige entschärfungen sind Lizenzverträge für Mitwirkende, benutzerfreundliche Lizenzen, Überprüfungen auf dem Stammbaum und unterstützende Grundlagen.

Die .net-Community hat sowohl plattformübergreifende als auch Open-Source-Unterstützung angenommen. .Net Core ist eine Open-Source-und plattformübergreifende Implementierung von .net, die auf einer Vielzahl von Plattformen ausgeführt wird, darunter Windows, macOS und verschiedene Linux-Distributionen. Xamarin stellt Mono, eine Open Source-Version von .net, bereit. Mono kann auf Android, IOS und einer Vielzahl anderer Formfaktoren, einschließlich Uhren und smarttvs, ausgeführt werden. Microsoft hat angekündigt, dass .net Core und Mono von .net [5](https://devblogs.microsoft.com/dotnet/introducing-net-5/) in eine einzelne .NET-Laufzeit und ein .NET-Framework abgestimmt werden, die überall verwendet werden können und die über einheitliche Laufzeitverhalten und Entwickler Erfahrung verfügen.

Werden ASP.net Web Forms von der Umstellung auf Open Source-und plattformübergreifende Unterstützung profitieren? Die Antwort ist leider nicht, oder zumindest nicht der gleiche Block wie der Rest der Plattform. Das .net-Team hat [vor kurzem fest](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/) stellen, dass ASP.net Web Forms nicht in .net Core oder .net 5 portiert werden. Warum ist das so?

In den frühen Tagen von .net Core zu portieren ASP.net Web Forms. Die Anzahl der erforderlichen wichtigen Änderungen wurde als zu drastisch festgestellt. Es gibt auch eine Möglichkeit, auch für Microsoft eine Beschränkung für die Anzahl der Webframe Works zu bieten, die es gleichzeitig unterstützen kann. Vielleicht nimmt jemand in der Community die Ursache für die Erstellung einer Open Source-und plattformübergreifenden Version von ASP.net Web Forms auf. Der [Quellcode für ASP.net Web Forms](https://github.com/microsoft/referencesource) wurde in einem Verweis Formular öffentlich verfügbar gemacht. Aber zu diesem Zeitpunkt scheint es ASP.net, Web Forms nur Windows und ohne ein Open-Source-Beitragsmodell beibehalten wird. Wenn plattformübergreifende Unterstützung oder Open-Source-Unterstützung für Ihre Szenarien wichtig ist, müssen Sie nach etwas neuem suchen.

Bedeutet dies, dass ASP.net Web Forms *inaktiv ist und* nicht mehr verwendet werden sollte? Natürlich nicht! Solange die .NET Framework als Teil von Windows ausgeliefert wird, ist ASP.net Web Forms ein unterstütztes Framework. Für viele Web Forms Entwickler ist die fehlende plattformübergreifende und Open Source-Unterstützung kein Problem. Wenn Sie keine plattformübergreifende Unterstützung, keine Open Source-Funktionen oder andere neue Funktionen in .net Core oder .net 5 benötigen, ist die Verwendung von ASP.net-Web Forms unter Windows in Ordnung. ASP.net Web Forms wird weiterhin eine produktive Möglichkeit zum Schreiben von Web-Apps für viele Jahre sein.

Es ist jedoch ein anderer Trend zu berücksichtigen, und das ist die Umstellung auf den Client.

## <a name="client-side-web-development"></a>Client seitige Webentwicklung

Alle. NET-basierte Webframe Works, einschließlich ASP.net-Web Forms, haben in der Vergangenheit eine gemeinsame Funktion: Sie sind *Server gerendert*. In vom Server gerenderten Web-Apps sendet der Browser eine Anforderung an den Server, der Code (.NET-Code in ASP.net-apps) ausführt, um eine Antwort zu erhalten. Diese Antwort wird zurück an den Browser gesendet, der verarbeitet werden soll. In diesem Modell wird der Browser als Thin Rendering-Engine verwendet. Die harte Arbeit bei der Erstellung der Benutzeroberfläche, beim Ausführen der Geschäftslogik und beim Verwalten des Zustands tritt auf dem Server auf.

Browser werden jedoch zu vielseitiger Plattformen. Sie implementieren eine ständig steigende Anzahl offener Webstandards, die den Zugriff auf die Funktionen des Computers des Benutzers ermöglichen. Warum können Sie die Rechenleistung, den Speicher, den Arbeitsspeicher und andere Ressourcen des Client Geräts nicht nutzen? Insbesondere Interaktionen mit der Benutzeroberfläche können von einem umfassenderen und interaktiven Gefühl profitieren, wenn Sie mindestens teilweise oder vollständig Client seitig behandelt werden. Logik und Daten, die auf dem Server behandelt werden sollen, können weiterhin serverseitig verarbeitet werden. Web-API-Aufrufe oder sogar über echt Zeitprotokolle, wie z. b. websockets, können verwendet werden. Diese Vorteile stehen Webentwicklern kostenlos zur Verfügung, wenn Sie bereit sind, JavaScript zu schreiben. Client seitige Benutzeroberflächen-Frameworks wie Angular, reagieren und Vue vereinfachen die Client seitige Webentwicklung und sind immer beliebter geworden. ASP.net Web Forms Entwickler können auch von der Nutzung des Clients profitieren und sogar über integrierte JavaScript-Frameworks wie ASP.NET AJAX verfügen.

Das Bridging von zwei verschiedenen Plattformen und Ökosystemen (.net und JavaScript) ist jedoch mit Kosten verbunden. Das Fachwissen ist in zwei parallelen Welten mit unterschiedlichen Sprachen, Frameworks und Tools erforderlich. Code und Logik können nicht einfach zwischen Client und Server freigegeben werden, was zu Duplizierung und Engineering-Aufwand führt. Es kann auch schwierig sein, mit dem JavaScript-Ökosystem Schritt zu halten, das den Verlauf der Entwicklung mit Break-Break-Geschwindigkeit hat. Das Front-End-Framework und die buildtooleinstellungen ändern sich schnell. Die Branche hat den Fortschritt von grunt zu Gulp zu WebPack und so weiter beobachtet. Die gleiche fehlerlose Abwanderung ist bei Front-End-Frameworks wie jQuery, Knockout, Angular, reagieren und Vue aufgetreten. Aber angesichts des Browser Monopols von JavaScript gab es kaum eine Auswahl. Das heißt, bis die webrolle vereint ist und ein *Wunder* ausgelöst hat!

## <a name="webassembly-fulfills-a-need"></a>Webassembly erfüllt einen Bedarf

In 2015 haben sich die wichtigsten Browserhersteller in einer W3C-Community-Gruppe gezwungen, einen neuen geöffneten Webstandard namens Webassembly zu erstellen. Webassembly ist ein Bytecode für das Web. Wenn Sie Ihren Code in Webassembly kompilieren können, kann er in einem beliebigen Browser auf jeder beliebigen Plattform mit nahezu nativer Geschwindigkeit ausgeführt werden. Anfängliche Bemühungen mit Schwerpunkt aufC++C/. Das Ergebnis war eine dramatische Demonstration der Ausführung nativer 3D-Grafikmodule direkt im Browser ohne Plug-ins. Webassembly wurde seitdem von allen wichtigen Browsern standardisiert und implementiert.

Die Ausführung von .net in Webassembly wurde in späterer 2017 angekündigt, und es wird erwartet, dass Sie 2020, einschließlich der Unterstützung von .net 5, ausgeliefert werden. Die Möglichkeit, .NET-Code direkt im Browser auszuführen, ermöglicht eine vollständige Webentwicklung mit .net.

## <a name="blazor-full-stack-web-development-with-net"></a>Blazor: vollständige Stapel basierte Webentwicklung mit .net

Die Möglichkeit, .NET-Code in einem Browser auszuführen, bietet keine End-to-End-Umgebung zum Erstellen von Client seitigen Web-Apps. An dieser Stelle kommt blazor ins Spiel. Blazor ist ein clientseitiges Framework für Webbenutzeroberflächen, das auf C# anstelle von JavaScript basiert. Blazor kann direkt im Browser über Webassembly ausgeführt werden. Es sind keine Browser-Plug-Ins erforderlich. Alternativ können blazor-apps serverseitig auf .net Core ausgeführt werden und alle Benutzerinteraktionen über eine Echtzeitverbindung mit dem Browser verarbeiten.

Blazor bietet hervorragend Unterstützung in Visual Studio und Visual Studio Code. Das Framework umfasst auch ein vollständiges UI-Komponentenmodell und verfügt über integrierte Funktionen für:

- Formulare und Überprüfung
- Dependency Injection
- Clientseitiges Routing
- Layouts
- Debuggen im Browser
- JavaScript-Interoperabilität

Blazor ist mit ASP.net Web Forms sehr häufig. Beide Frameworks bieten komponentenbasierte, ereignisgesteuerte, Zustands behaftete UI-Programmier Modelle. Der wesentliche Unterschied bei der Architektur besteht darin, dass ASP.net Web Forms nur auf dem Server ausgeführt wird. Blazor kann auf dem Client im Browser ausgeführt werden. Wenn Sie jedoch aus einem ASP.net-Web Forms Hintergrund kommen, gibt es eine Menge in blazor, die sich vertraut machen wird. Blazor ist eine natürliche Lösung für ASP.net Web Forms-Entwicklern, die eine Möglichkeit zum Nutzen der Client seitigen Entwicklung und der plattformübergreifenden Open Source-Entwicklung von .net suchen.

Dieses Buch bietet eine Einführung in blazor, das speziell für ASP.net Web Forms-Entwicklern berücksichtigt wird. Jedes blazor-Konzept wird im Kontext von Analog ASP.net Web Forms Features und Verfahren präsentiert. Am Ende dieses Buchs haben Sie Folgendes Verständnis:

- Erfahren Sie, wie Sie blazor-Apps erstellen.
- Funktionsweise von blazor
- So bezieht sich blazor auf .net Core.
- Angemessene Strategien für die Migration vorhandener ASP.net Web Forms-apps zu blazor, wenn dies angebracht ist.

## <a name="get-started-with-blazor"></a>Einstieg in blazor

Der Einstieg in blazor ist einfach. Wechseln Sie zu <https://blazor.net>, und befolgen Sie die Links, um die entsprechenden .net Core SDK-und blazor-Projektvorlagen zu installieren. Außerdem finden Sie Anweisungen zum Einrichten der blazor-Tools in Visual Studio oder Visual Studio Code.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](architecture-comparison.md)
