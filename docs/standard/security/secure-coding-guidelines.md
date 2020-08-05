---
title: Sichere Codierungs Richtlinien für .net
description: Entwerfen Sie Code, mit dem Sie arbeiten können. Durch das Netzwerk erzwungene Berechtigungen und andere Erzwingung, um zu verhindern, dass bösartiger Code auf Daten zugreift oder andere Aktionen ausführt.
ms.date: 07/15/2020
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
ms.openlocfilehash: a05e0cec2814be88ac835d05601d5cf5f66383c3
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555955"
---
# <a name="secure-coding-guidelines"></a>Sichere Codierungs Richtlinien

In den meisten Anwendungs Codes kann einfach die von .net implementierte Infrastruktur verwendet werden. In einigen Fällen ist eine zusätzliche anwendungsspezifische Sicherheit erforderlich, die entweder durch Erweitern des Sicherheitssystems oder mithilfe neuer Ad-hoc-Methoden erstellt wird.

Mithilfe von .net-erzwungenen Berechtigungen und anderer Erzwingung in Ihrem Code sollten Sie Barrieren errichten, um zu verhindern, dass bösartiger Code auf Informationen zugreifen kann, die er nicht haben oder andere unerwünschte Aktionen ausführen soll. Darüber hinaus müssen Sie mithilfe von vertrauenswürdigem Code ein Gleichgewicht zwischen Sicherheit und Nutzbarkeit herstellen.

In dieser Übersicht werden die verschiedenen Methoden zum Entwerfen von Code beschrieben, damit dieser mit dem Sicherheitssystem funktioniert.

## <a name="securing-resource-access"></a>Sichern des Ressourcen Zugriffs

Beim Entwerfen und Schreiben von Code müssen Sie den Zugriff, den Code auf Ressourcen hat, schützen und einschränken. Dies gilt insbesondere, wenn Code mit unbekannter Herkunft verwendet oder aufgerufen wird. Daher sollten Sie die folgenden Aspekte beachten, um sicherzustellen, dass Ihr Code sicher ist:

- Verwenden Sie nicht die Codezugriffssicherheit (Code Access Security, CAS).

- Verwenden Sie keinen teilweise vertrauenswürdigen Code.

- Verwenden Sie das [allowpartiallytrust dcaller](xref:System.Security.AllowPartiallyTrustedCallersAttribute) -Attribut (APTCA) nicht.

- Verwenden Sie nicht .NET-Remoting.

- Verwenden Sie nicht DCOM (Distributed Component Object Model).

- Verwenden Sie keine binären Formatierungsprogramme.

Code Zugriffssicherheit und Sicherheits transparenter Code werden als Sicherheitsgrenze mit teilweise vertrauenswürdigem Code nicht unterstützt. Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen. Die alternativen Sicherheitsmaßnahmen sind:

- Virtualisierung

- AppContainer

- Betriebssystembenutzer und -berechtigungen

- Hyper-V-Container

## <a name="security-neutral-code"></a>Sicherheits neutraler Code

Sicherheitsneutraler Code wirkt sich nicht explizit auf das Sicherheitssystem aus. Er wird mit den jeweiligen Berechtigungen ausgeführt, die er erhält. Obwohl Anwendungen, die keine Sicherheits Ausnahmen abfangen können (z. b. die Verwendung von Dateien, Netzwerken usw.), zu einer nicht behandelten Ausnahme führen können, nutzt der Sicherheits neutrale Code weiterhin die Sicherheitstechnologien in .net.

Eine sicherheitsneutrale Bibliothek weist besondere Merkmale auf, die Sie kennen sollten. Angenommen, Ihre Bibliothek stellt API-Elemente bereit, die Dateien verwenden oder nicht verwalteten Code aufgerufen haben. Wenn Ihr Code nicht über die entsprechende Berechtigung verfügt, wird er nicht wie beschrieben ausgeführt. Auch wenn der Code über die Berechtigung verfügt, muss jeder ihn aufrufende Anwendungscode über dieselbe Berechtigung verfügen, damit er funktioniert. Wenn der aufrufende Code nicht die richtige Berechtigung hat, wird <xref:System.Security.SecurityException> als Ergebnis des Stackwalk für die Code Zugriffssicherheit eine angezeigt.

## <a name="application-code-that-isnt-a-reusable-component"></a>Anwendungscode, der keine wiederverwendbare Komponente ist

Wenn Ihr Code Teil einer Anwendung ist, die nicht von anderem Code aufgerufen wird, ist die Sicherheit einfach, und spezielle Codierungen sind möglicherweise nicht erforderlich. Beachten Sie jedoch, dass Ihr Code von schädlichem Code aufgerufen werden kann. Obwohl die Codezugriffssicherheit möglicherweise den Zugriff auf Ressourcen durch schädlichen Code beenden kann, könnte dieser Code weiterhin Werte Ihrer Felder oder Eigenschaften lesen, die möglicherweise vertrauliche Informationen enthalten.

Darüber hinaus müssen Sie hinsichtlich schädlicher Eingaben vorsichtig sein, wenn Ihr Code Benutzereingaben aus dem Internet oder anderen unzuverlässigen Quellen akzeptiert.

## <a name="managed-wrapper-to-native-code-implementation"></a>Implementierung von verwaltetem Wrapper in nativem Code

In diesem Szenario werden in der Regel einige nützliche Funktionen in systemeigenem Code implementiert, die Sie für verwalteten Code verfügbar machen können. Verwaltete Wrapper sind mithilfe von Plattformaufrufen oder COM-Interops einfach zu schreiben. Wenn Sie auf diese Weise vorgehen, müssen die Aufrufer der Wrapper über Berechtigungen für nicht verwalteten Code verfügen, um erfolgreich agieren zu können. In der Standard Richtlinie bedeutet dies, dass der aus einem Intranet oder dem Internet heruntergeladene Code mit den Wrappern nicht funktioniert.

Anstatt allen Anwendungen, die diese Wrapper verwenden, Berechtigungen für nicht verwalteten Code zu gewähren, ist es besser, diese Rechte nur dem Wrapper Code zuzuweisen. Wenn die zugrunde liegenden Funktionen keine Ressourcen verfügbar machen und die Implementierung entsprechend sicher ist, muss der Wrapper nur seine Rechte bestätigen, wodurch Aufrufe von beliebigem Code über den Wrapper ermöglicht werden. Wenn Ressourcen einbezogen sind, sollte die Codierung der Sicherheit mit der im Bibliothekscodefall verwendeten Codierung identisch sein, der im nächsten Abschnitt beschrieben wird. Da der Wrapper Aufrufer dieser Ressourcen potenziell verfügbar macht, ist eine sorgfältige Überprüfung der Sicherheit des systemeigenen Codes erforderlich, für die der Wrapper zuständig ist.

## <a name="library-code-that-exposes-protected-resources"></a>Bibliotheks Code zur Offenlegung geschützter Ressourcen

Der folgende Ansatz ist die leistungsfähigste und daher potenziell gefährlich (falls falsch) für die Sicherheits Codierung: Ihre Bibliothek fungiert als Schnittstelle für anderen Code für den Zugriff auf bestimmte Ressourcen, die anderweitig nicht verfügbar sind, ebenso wie die .NET-Klassen Berechtigungen für die Ressourcen erzwingen, die Sie verwenden. Überall dort, wo Sie eine Ressource verfügbar machen, muss der Code zunächst die für die Ressource geeignete Berechtigung anfordern (d. h. er muss eine Sicherheitsüberprüfung durchführen) und seine Rechte dann in der Regel bestätigen, um den eigentlichen Vorgang ausführen zu können.

## <a name="see-also"></a>Weitere Informationen

- [Sichern von Statusdaten](securing-state-data.md)
- [Sicherheit und Benutzereingaben](security-and-user-input.md)
- [Sicherheit und Racebedingungen](security-and-race-conditions.md)
- [Sicherheit und dynamische Codegenerierung](security-and-on-the-fly-code-generation.md)
- [Rollenbasierte Sicherheit](role-based-security.md)
- [ASP.net Core Sicherheit](/aspnet/core/security/)
