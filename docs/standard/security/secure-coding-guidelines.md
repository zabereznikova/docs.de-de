---
title: Richtlinien für das Schreiben von sicherem Code
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- managed wrapper to native code implementation
- secure coding
- reusable components
- library code that exposes protected resources
- code, security
- code security
- secure coding, options
- components [.NET Framework], security
- code security, options
- security-neutral code
- security [.NET Framework], coding guidelines
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8d61e76a657c7341ec7dfcede6d7dc9943d4659
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588160"
---
# <a name="secure-coding-guidelines"></a>Richtlinien für das Schreiben von sicherem Code
Die nachweisbasierte Sicherheit und die Codezugriffssicherheit bieten sehr leistungsstarke, explizite Mechanismen zum Implementieren der Sicherheit. Der Großteil des Anwendungscodes kann einfach die von .NET Framework implementierte Infrastruktur verwenden. In einigen Fällen ist eine zusätzliche anwendungsspezifische Sicherheit erforderlich, die entweder durch Erweitern des Sicherheitssystems oder mithilfe neuer Ad-hoc-Methoden erstellt wird.  
  
 Mithilfe der mit .NET Framework durchgesetzten Berechtigungen und den sonstigen Durchsetzungen im Code sollten Sie Barrieren errichten, um zu verhindern, dass vertrauliche Informationen über schädlichen Code abgerufen oder andere unerwünschte Aktionen ausgeführt werden. Darüber hinaus müssen Sie mithilfe von vertrauenswürdigem Code ein Gleichgewicht zwischen Sicherheit und Nutzbarkeit herstellen.  
  
 In dieser Übersicht werden die verschiedenen Methoden zum Entwerfen von Code beschrieben, damit dieser mit dem Sicherheitssystem funktioniert.  
  
## <a name="securing-resource-access"></a>Schützen von Ressourcenzugriff  
 Beim Entwerfen und Schreiben von Code müssen Sie den Zugriff, den Code auf Ressourcen hat, schützen und einschränken. Dies gilt insbesondere, wenn Code mit unbekannter Herkunft verwendet oder aufgerufen wird. Daher sollten Sie die folgenden Aspekte beachten, um sicherzustellen, dass Ihr Code sicher ist:  
  
-   Verwenden Sie nicht die Codezugriffssicherheit (Code Access Security, CAS).  
  
-   Verwenden Sie keinen teilweise vertrauenswürdigen Code.  
  
-   Verwenden Sie nicht .NET-Remoting.  
  
-   Verwenden Sie nicht DCOM (Distributed Component Object Model).  
  
-   Verwenden Sie keine binären Formatierungsprogramme.  
  
 Codezugriffssicherheit und sicherheitstransparenter Code werden bei teilweise vertrauenswürdigem Code nicht als Sicherheitsgrenze unterstützt. Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen. Die alternativen Sicherheitsmaßnahmen sind:  
  
-   Virtualisierung  
  
-   AppContainer  
  
-   Betriebssystembenutzer und -berechtigungen  
  
-   Hyper-V-Container  
  
## <a name="security-neutral-code"></a>Sicherheitsneutraler Code  
 Sicherheitsneutraler Code wirkt sich nicht explizit auf das Sicherheitssystem aus. Er wird mit den jeweiligen Berechtigungen ausgeführt, die er erhält. Obwohl Anwendungen, die keine zu geschützten Operationen (z. B. die Verwendung von Dateien, Netzwerkfunktionen usw.) zugeordneten Sicherheitsausnahmen abfangen können, zu einer nicht behandelten Ausnahme führen können, nutzt der sicherheitsneutrale Code weiterhin die .NET Framework-Sicherheitstechnologien.  
  
 Eine sicherheitsneutrale Bibliothek weist besondere Merkmale auf, die Sie kennen sollten. Angenommen, Ihre Bibliothek stellt API-Elemente bereit, die Dateien verwenden oder nicht verwalteten Code aufrufen. Wenn der Code nicht über die entsprechende Berechtigung verfügt, wird er nicht wie beschrieben ausgeführt. Auch wenn der Code über die Berechtigung verfügt, muss jeder ihn aufrufende Anwendungscode über dieselbe Berechtigung verfügen, damit er funktioniert. Wenn der aufrufende Code nicht die richtige Berechtigung verfügt ein <xref:System.Security.SecurityException> wird angezeigt, weil der Code Access Security Stackwalk.  
  
## <a name="application-code-that-is-not-a-reusable-component"></a>Anwendungscode, der keine wiederverwendbare Komponente darstellt  
 Wenn Ihr Code Teil einer Anwendung ist, die nicht von anderem Code aufgerufen wird, ist die Sicherheit einfach zu erreichen und möglicherweise keine spezielle Codierung erforderlich. Beachten Sie jedoch, dass Ihr Code von schädlichem Code aufgerufen werden kann. Obwohl die Codezugriffssicherheit möglicherweise den Zugriff auf Ressourcen durch schädlichen Code beenden kann, könnte dieser Code weiterhin Werte Ihrer Felder oder Eigenschaften lesen, die möglicherweise vertrauliche Informationen enthalten.  
  
 Darüber hinaus müssen Sie hinsichtlich schädlicher Eingaben vorsichtig sein, wenn Ihr Code Benutzereingaben aus dem Internet oder anderen unzuverlässigen Quellen akzeptiert.  
  
## <a name="managed-wrapper-to-native-code-implementation"></a>Implementierung von verwalteten Wrappern für systemeigenen Code  
 In diesem Szenario werden in der Regel einige nützliche Funktionen in systemeigenem Code implementiert, die Sie für verwalteten Code verfügbar machen können. Verwaltete Wrapper sind mithilfe von Plattformaufrufen oder COM-Interops einfach zu schreiben. Wenn Sie auf diese Weise vorgehen, müssen die Aufrufer der Wrapper über Berechtigungen für nicht verwalteten Code verfügen, um erfolgreich agieren zu können. Entsprechend der Standardrichtlinie bedeutet dies, dass der aus einem Intranet oder dem Internet heruntergeladene Code mit den Wrappern nicht funktioniert.  
  
 Anstatt allen Anwendungen, die diese Wrapper verwenden, die Berechtigungen für nicht verwalteten Code zu gewähren, ist es besser, diese Berechtigungen nur dem Wrappercode zuzuordnen. Wenn die zugrunde liegenden Funktionen keine Ressourcen verfügbar machen und die Implementierung entsprechend sicher ist, muss der Wrapper nur seine Rechte bestätigen, wodurch Aufrufe von beliebigem Code über den Wrapper ermöglicht werden. Wenn Ressourcen einbezogen sind, sollte die Codierung der Sicherheit mit der im Bibliothekscodefall verwendeten Codierung identisch sein, der im nächsten Abschnitt beschrieben wird. Da der Wrapper Aufrufer dieser Ressourcen potenziell verfügbar macht, ist eine sorgfältige Überprüfung der Sicherheit des systemeigenen Codes erforderlich, für die der Wrapper zuständig ist.  
  
## <a name="library-code-that-exposes-protected-resources"></a>Bibliothekscode zur Offenlegung geschützter Ressourcen  
 Dies ist der leistungsstärkste und daher möglicherweise ein gefährlicher Ansatz (bei falscher Durchführung) für Sicherheitscode: Ihre Bibliothek fungiert hier als Schnittstelle für anderen Code für den Zugriff auf bestimmte Ressourcen, die anderweitig nicht verfügbar sind, ebenso wie die Klassen von .NET Framework die Berechtigungen für die Ressourcen erzwingen, die sie verwenden. Überall dort, wo Sie eine Ressource verfügbar machen, muss der Code zunächst die für die Ressource geeignete Berechtigung anfordern (d. h. er muss eine Sicherheitsüberprüfung durchführen) und seine Rechte dann in der Regel bestätigen, um den eigentlichen Vorgang ausführen zu können.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Sichern von Statusdaten](../../../docs/standard/security/securing-state-data.md)|Beschreibt, wie private Member geschützt werden.|  
|[Sicherheit und Benutzereingaben](../../../docs/standard/security/security-and-user-input.md)|Beschreibt die Sicherheitsrisiken für Anwendungen, die Benutzereingaben akzeptieren.|  
|[Sicherheit und Racebedingungen](../../../docs/standard/security/security-and-race-conditions.md)|Beschreibt, wie Racebedingungen im Code vermieden werden.|  
|[Sicherheit und dynamische Codegenerierung](../../../docs/standard/security/security-and-on-the-fly-code-generation.md)|Beschreibt die Sicherheitsrisiken für Anwendungen, die dynamischen Code generieren.|  
|[Rollenbasierte Sicherheit](../../../docs/standard/security/role-based-security.md)|Beschreibt die rollenbasierte .NET Framework-Sicherheit ausführlich und bietet Anweisungen zu deren Verwendung im Code.|
