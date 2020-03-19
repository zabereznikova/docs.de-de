---
title: Sichere Codierungsrichtlinien für .NET
description: Entwerfen Sie Code, mit dem gearbeitet werden soll. NET-erzwungene Berechtigungen und andere Erzwingung, um zu verhindern, dass bösartiger Code auf Daten zugreift oder andere Aktionen ausführt.
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
ms.openlocfilehash: 05f7e039ecdc0cd33baa015872924fb9e1f078aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187729"
---
# <a name="secure-coding-guidelines"></a>Sichere Codierungsrichtlinien

Die nachweisbasierte Sicherheit und die Codezugriffssicherheit bieten sehr leistungsstarke, explizite Mechanismen zum Implementieren der Sicherheit. Die meisten Anwendungscodes können einfach die von .NET implementierte Infrastruktur verwenden. In einigen Fällen ist eine zusätzliche anwendungsspezifische Sicherheit erforderlich, die entweder durch Erweitern des Sicherheitssystems oder mithilfe neuer Ad-hoc-Methoden erstellt wird.

Mithilfe von .NET erzwungenen Berechtigungen und anderer Erzwingung in Ihrem Code sollten Sie Barrieren errichten, um zu verhindern, dass böswilliger Code auf Informationen zugreift, die sie nicht haben sollen, oder andere unerwünschte Aktionen ausführen. Darüber hinaus müssen Sie mithilfe von vertrauenswürdigem Code ein Gleichgewicht zwischen Sicherheit und Nutzbarkeit herstellen.

In dieser Übersicht werden die verschiedenen Methoden zum Entwerfen von Code beschrieben, damit dieser mit dem Sicherheitssystem funktioniert.

## <a name="securing-resource-access"></a>Sichern des Ressourcenzugriffs

Beim Entwerfen und Schreiben von Code müssen Sie den Zugriff, den Code auf Ressourcen hat, schützen und einschränken. Dies gilt insbesondere, wenn Code mit unbekannter Herkunft verwendet oder aufgerufen wird. Daher sollten Sie die folgenden Aspekte beachten, um sicherzustellen, dass Ihr Code sicher ist:

- Verwenden Sie nicht die Codezugriffssicherheit (Code Access Security, CAS).

- Verwenden Sie keinen teilweise vertrauenswürdigen Code.

- Verwenden Sie nicht das [AllowPartiallyTrustedCaller-Attribut](xref:System.Security.AllowPartiallyTrustedCallersAttribute) (APTCA).

- Verwenden Sie nicht .NET-Remoting.

- Verwenden Sie nicht DCOM (Distributed Component Object Model).

- Verwenden Sie keine binären Formatierungsprogramme.

Codezugriffssicherheit und sicherheitstransparenter Code werden nicht als Sicherheitsgrenze mit teilweise vertrauenswürdigem Code unterstützt. Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen. Die alternativen Sicherheitsmaßnahmen sind:

- Virtualisierung

- AppContainer

- Betriebssystembenutzer und -berechtigungen

- Hyper-V-Container

## <a name="security-neutral-code"></a>Sicherheitsneutraler Code

Sicherheitsneutraler Code wirkt sich nicht explizit auf das Sicherheitssystem aus. Er wird mit den jeweiligen Berechtigungen ausgeführt, die er erhält. Obwohl Anwendungen, die Sicherheitsausnahmen im Zusammenhang mit geschützten Vorgängen nicht abfangen (z. B. die Verwendung von Dateien, Netzwerken usw.), zu einer nicht behandelten Ausnahme führen können, nutzt sicherheitsneutraler Code weiterhin die Sicherheitstechnologien in .NET .

Eine sicherheitsneutrale Bibliothek weist besondere Merkmale auf, die Sie kennen sollten. Angenommen, Ihre Bibliothek stellt API-Elemente bereit, die Dateien verwenden oder nicht verwalteten Code aufrufen. Wenn Ihr Code nicht über die entsprechende Berechtigung verfügt, wird er nicht wie beschrieben ausgeführt. Auch wenn der Code über die Berechtigung verfügt, muss jeder ihn aufrufende Anwendungscode über dieselbe Berechtigung verfügen, damit er funktioniert. Wenn der aufrufende Code nicht über <xref:System.Security.SecurityException> die richtige Berechtigung verfügt, wird als Ergebnis des Codezugriffs-Sicherheitsstapels eine angezeigt.

## <a name="application-code-that-isnt-a-reusable-component"></a>Anwendungscode, der keine wiederverwendbare Komponente ist

Wenn Ihr Code Teil einer Anwendung ist, die nicht von anderem Code aufgerufen wird, ist die Sicherheit einfach, und eine spezielle Codierung ist möglicherweise nicht erforderlich. Beachten Sie jedoch, dass Ihr Code von schädlichem Code aufgerufen werden kann. Obwohl die Codezugriffssicherheit möglicherweise den Zugriff auf Ressourcen durch schädlichen Code beenden kann, könnte dieser Code weiterhin Werte Ihrer Felder oder Eigenschaften lesen, die möglicherweise vertrauliche Informationen enthalten.

Darüber hinaus müssen Sie hinsichtlich schädlicher Eingaben vorsichtig sein, wenn Ihr Code Benutzereingaben aus dem Internet oder anderen unzuverlässigen Quellen akzeptiert.

## <a name="managed-wrapper-to-native-code-implementation"></a>Verwalteter Wrapper für die implementierung von systemeigenem Code

In diesem Szenario werden in der Regel einige nützliche Funktionen in systemeigenem Code implementiert, die Sie für verwalteten Code verfügbar machen können. Verwaltete Wrapper sind mithilfe von Plattformaufrufen oder COM-Interops einfach zu schreiben. Wenn Sie auf diese Weise vorgehen, müssen die Aufrufer der Wrapper über Berechtigungen für nicht verwalteten Code verfügen, um erfolgreich agieren zu können. Unter der Standardrichtlinie bedeutet dies, dass Code, der aus einem Intranet oder dem Internet heruntergeladen wurde, nicht mit den Wrappern funktioniert.

Anstatt nicht verwalteten Coderechten allen Anwendungen zu gewähren, die diese Wrapper verwenden, ist es besser, diese Rechte nur dem Wrappercode zu gewähren. Wenn die zugrunde liegenden Funktionen keine Ressourcen verfügbar machen und die Implementierung entsprechend sicher ist, muss der Wrapper nur seine Rechte bestätigen, wodurch Aufrufe von beliebigem Code über den Wrapper ermöglicht werden. Wenn Ressourcen einbezogen sind, sollte die Codierung der Sicherheit mit der im Bibliothekscodefall verwendeten Codierung identisch sein, der im nächsten Abschnitt beschrieben wird. Da der Wrapper Aufrufer dieser Ressourcen potenziell verfügbar macht, ist eine sorgfältige Überprüfung der Sicherheit des systemeigenen Codes erforderlich, für die der Wrapper zuständig ist.

## <a name="library-code-that-exposes-protected-resources"></a>Bibliothekscode, der geschützte Ressourcen verfügbar macht

Der folgende Ansatz ist der leistungsstärkste und daher potenziell gefährlich (wenn falsch durchgeführt) für die Sicherheitscodierung: Ihre Bibliothek dient als Schnittstelle für anderen Code, um auf bestimmte Ressourcen zuzugreifen, die sonst nicht verfügbar sind, so wie die .NET-Klassen erzwingen. Berechtigungen für die Ressourcen, die sie verwenden. Überall dort, wo Sie eine Ressource verfügbar machen, muss der Code zunächst die für die Ressource geeignete Berechtigung anfordern (d. h. er muss eine Sicherheitsüberprüfung durchführen) und seine Rechte dann in der Regel bestätigen, um den eigentlichen Vorgang ausführen zu können.

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Sichern von Statusdaten](securing-state-data.md)|Beschreibt, wie private Member geschützt werden.|
|[Sicherheit und Benutzereingaben](security-and-user-input.md)|Beschreibt die Sicherheitsrisiken für Anwendungen, die Benutzereingaben akzeptieren.|
|[Sicherheit und Racebedingungen](security-and-race-conditions.md)|Beschreibt, wie Racebedingungen im Code vermieden werden.|
|[Sicherheit und dynamische Codegenerierung](security-and-on-the-fly-code-generation.md)|Beschreibt die Sicherheitsrisiken für Anwendungen, die dynamischen Code generieren.|
|[Rollenbasierte Sicherheit](role-based-security.md)|Beschreibt die rollenbasierte Sicherheit von .NET im Detail und enthält Anweisungen für die Verwendung in Ihrem Code.|
