---
title: Sichern von Programmierungsrichtlinien für .NET
ms.date: 06/28/2018
helpviewer_keywords:
- managed wrapper to native code implementation
- secure coding
- reusable components
- library code that exposes protected resources
- code, security
- code security
- secure coding, options
- components [.NET], security
- code security, options
- security-neutral code
- security [.NET], coding guidelines
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3a8f0dfc1a2b5e09722876b73281ed1d8b6334e
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106735"
---
# <a name="secure-coding-guidelines"></a>Sicheren Sie Richtlinien für Code

Die nachweisbasierte Sicherheit und die Codezugriffssicherheit bieten sehr leistungsstarke, explizite Mechanismen zum Implementieren der Sicherheit. Großteil des Anwendungscodes kann einfach die Infrastruktur von .NET verwenden. In einigen Fällen ist eine zusätzliche anwendungsspezifische Sicherheit erforderlich, die entweder durch Erweitern des Sicherheitssystems oder mithilfe neuer Ad-hoc-Methoden erstellt wird.

Mithilfe von .NET erzwungen, Berechtigungen und den anderen in Ihrem Code, Sie sollten Barrieren errichten um vertrauliche zu verhindern, dass bösartigen Code aus den Zugriff auf Informationen, die es haben möchten, oder andere unerwünschte Aktionen ausgeführt. Darüber hinaus müssen Sie mithilfe von vertrauenswürdigem Code ein Gleichgewicht zwischen Sicherheit und Nutzbarkeit herstellen.

In dieser Übersicht werden die verschiedenen Methoden zum Entwerfen von Code beschrieben, damit dieser mit dem Sicherheitssystem funktioniert.

## <a name="securing-resource-access"></a>Sichern von Ressourcenzugriff

Beim Entwerfen und Schreiben von Code müssen Sie den Zugriff, den Code auf Ressourcen hat, schützen und einschränken. Dies gilt insbesondere, wenn Code mit unbekannter Herkunft verwendet oder aufgerufen wird. Daher sollten Sie die folgenden Aspekte beachten, um sicherzustellen, dass Ihr Code sicher ist:

- Verwenden Sie nicht die Codezugriffssicherheit (Code Access Security, CAS).

- Verwenden Sie keinen teilweise vertrauenswürdigen Code.

- Verwenden Sie nicht die [AllowPartiallyTrustedCaller](xref:System.Security.AllowPartiallyTrustedCallersAttribute) -Attribut (APTCA).

- Verwenden Sie nicht .NET-Remoting.

- Verwenden Sie nicht DCOM (Distributed Component Object Model).

- Verwenden Sie keine binären Formatierungsprogramme.

Codezugriffssicherheit und Sicherheitstransparenter Code werden als sicherheitsbegrenzung bei teilweise vertrauenswürdigem Code nicht unterstützt. Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen. Die alternativen Sicherheitsmaßnahmen sind:

- Virtualisierung

- AppContainer

- Betriebssystembenutzer und -berechtigungen

- Hyper-V-Container

## <a name="security-neutral-code"></a>Sicherheitsneutraler code

Sicherheitsneutraler Code wirkt sich nicht explizit auf das Sicherheitssystem aus. Er wird mit den jeweiligen Berechtigungen ausgeführt, die er erhält. Obwohl Anwendungen, die nicht geschützten Operationen (z. B. Dateien, Netzwerke usw.) zugeordnete Sicherheitsausnahmen Abfangen einer nicht behandelten Ausnahme führen können, nutzt sicherheitsneutrale Code weiterhin den sicherheitstechnologien in .NET .

Eine sicherheitsneutrale Bibliothek weist besondere Merkmale auf, die Sie kennen sollten. Angenommen Sie, Ihre Bibliothek API-Elemente bereitstellt, die mit Dateien verwenden oder nicht verwalteten Code aufrufen. Wenn Codes über die entsprechende Berechtigung verfügt, wird er nicht ausgeführt wie beschrieben. Auch wenn der Code über die Berechtigung verfügt, muss jeder ihn aufrufende Anwendungscode über dieselbe Berechtigung verfügen, damit er funktioniert. Wenn der aufrufende Code die entsprechende Berechtigung besitzt eine <xref:System.Security.SecurityException> wird angezeigt, weil der Code Access Security Stackwalk.

## <a name="application-code-that-isnt-a-reusable-component"></a>Anwendungscode, der eine wiederverwendbare Komponente ist nicht

Wenn Ihr Code Teil einer Anwendung, die wird nicht von anderem Code aufgerufen werden ist, Sicherheit ist einfach, und spezielle Codierung möglicherweise nicht erforderlich. Beachten Sie jedoch, dass Ihr Code von schädlichem Code aufgerufen werden kann. Obwohl die Codezugriffssicherheit möglicherweise den Zugriff auf Ressourcen durch schädlichen Code beenden kann, könnte dieser Code weiterhin Werte Ihrer Felder oder Eigenschaften lesen, die möglicherweise vertrauliche Informationen enthalten.

Darüber hinaus müssen Sie hinsichtlich schädlicher Eingaben vorsichtig sein, wenn Ihr Code Benutzereingaben aus dem Internet oder anderen unzuverlässigen Quellen akzeptiert.

## <a name="managed-wrapper-to-native-code-implementation"></a>Von verwalteten Wrappern für systemeigenen Code-Implementierung

In diesem Szenario werden in der Regel einige nützliche Funktionen in systemeigenem Code implementiert, die Sie für verwalteten Code verfügbar machen können. Verwaltete Wrapper sind mithilfe von Plattformaufrufen oder COM-Interops einfach zu schreiben. Wenn Sie auf diese Weise vorgehen, müssen die Aufrufer der Wrapper über Berechtigungen für nicht verwalteten Code verfügen, um erfolgreich agieren zu können. Entsprechend der Standardrichtlinie bedeutet dies, dass Code von einem Intranet heruntergeladen oder das Internet mit den Wrappern funktioniert nicht.

Anstatt mit nicht verwaltetem Code Rechte für alle Anwendungen, die diese Wrapper verwenden, ist es besser, diese Berechtigungen nur dem Wrappercode zu erteilen. Wenn die zugrunde liegenden Funktionen keine Ressourcen verfügbar machen und die Implementierung entsprechend sicher ist, muss der Wrapper nur seine Rechte bestätigen, wodurch Aufrufe von beliebigem Code über den Wrapper ermöglicht werden. Wenn Ressourcen einbezogen sind, sollte die Codierung der Sicherheit mit der im Bibliothekscodefall verwendeten Codierung identisch sein, der im nächsten Abschnitt beschrieben wird. Da der Wrapper Aufrufer dieser Ressourcen potenziell verfügbar macht, ist eine sorgfältige Überprüfung der Sicherheit des systemeigenen Codes erforderlich, für die der Wrapper zuständig ist.

## <a name="library-code-that-exposes-protected-resources"></a>Bibliothekscode zur Offenlegung geschützter Ressourcen

Der folgende Ansatz ist der leistungsstärkste und daher potenziell gefährlichen (bei falscher) für Sicherheitscode: Ihre Bibliothek fungiert hier als Schnittstelle für anderen Code auf bestimmte Ressourcen zugreifen, die andernfalls nicht zur Verfügung stehen, ebenso wie die .NET Klassen erzwingen Berechtigungen für die Ressourcen, die sie verwenden. Überall dort, wo Sie eine Ressource verfügbar machen, muss der Code zunächst die für die Ressource geeignete Berechtigung anfordern (d. h. er muss eine Sicherheitsüberprüfung durchführen) und seine Rechte dann in der Regel bestätigen, um den eigentlichen Vorgang ausführen zu können.

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Sichern von Statusdaten](securing-state-data.md)|Beschreibt, wie private Member geschützt werden.|
|[Sicherheit und Benutzereingaben](security-and-user-input.md)|Beschreibt die Sicherheitsrisiken für Anwendungen, die Benutzereingaben akzeptieren.|
|[Sicherheit und Racebedingungen](security-and-race-conditions.md)|Beschreibt, wie Racebedingungen im Code vermieden werden.|
|[Sicherheit und dynamische Codegenerierung](security-and-on-the-fly-code-generation.md)|Beschreibt die Sicherheitsrisiken für Anwendungen, die dynamischen Code generieren.|
|[Rollenbasierte Sicherheit](role-based-security.md)|Beschreibt die .NET mit der rollenbasierten Sicherheit ausführlich und bietet Anweisungen zu deren Verwendung im Code.|
