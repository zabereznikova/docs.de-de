---
title: "Secure Coding Guidelines | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "managed wrapper to native code implementation"
  - "secure coding"
  - "reusable components"
  - "library code that exposes protected resources"
  - "code, security"
  - "code security"
  - "secure coding, options"
  - "components [.NET Framework], security"
  - "code security, options"
  - "security-neutral code"
  - "security [.NET Framework], coding guidelines"
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
caps.latest.revision: 20
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Secure Coding Guidelines
Die nachweisbasierte Sicherheit und die Codezugriffssicherheit bieten sehr leistungsstarke, explizite Mechanismen zum Implementieren der Sicherheit. Der Großteil des Anwendungscodes kann einfach die von .NET Framework implementierte Infrastruktur verwenden. In einigen Fällen ist eine zusätzliche anwendungsspezifische Sicherheit erforderlich, die entweder durch Erweitern des Sicherheitssystems oder mithilfe neuer Ad\-hoc\-Methoden erstellt wird.  
  
 Mithilfe der mit .NET Framework durchgesetzten Berechtigungen und den sonstigen Durchsetzungen im Code sollten Sie Barrieren errichten, um zu verhindern, dass vertrauliche Informationen über schädlichen Code abgerufen oder andere unerwünschte Aktionen ausgeführt werden. Darüber hinaus müssen Sie mithilfe von vertrauenswürdigem Code ein Gleichgewicht zwischen Sicherheit und Nutzbarkeit herstellen.  
  
 In dieser Übersicht werden die verschiedenen Methoden zum Entwerfen von Code beschrieben, damit dieser mit dem Sicherheitssystem funktioniert.  
  
> [!NOTE]
>  In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] wurden wichtige Änderungen am Sicherheitsmodell und an der Terminologie von .NET Framework vorgenommen. Weitere Informationen zu diesen Änderungen finden Sie unter [Sicherheitsänderungen](../../../docs/framework/security/security-changes.md).  
  
## Codezugriffssicherheit und teilweise vertrauenswürdiger Code  
 .NET Framework bietet einen Mechanismus namens Codezugriffssicherheit \(Code Access Security, CAS\) zur Erzwingung verschiedener Vertrauensebenen für anderen Code, der in der gleichen Anwendung ausgeführt wird.  Da die Codezugriffssicherheit in .NET Framework keine Codeisolierung gewährleistet, sollte sie nicht als Sicherheitsbegrenzung bei teilweise vertrauenswürdigem Code verwendet werden. Dies gilt insbesondere für Code unbekannter Herkunft. Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen.  
  
 Diese Richtlinie gilt für alle Versionen von .NET Framework, außer für die in Silverlight enthaltene .NET Framework\-Version.  
  
## Sicherheitsneutraler Code  
 Sicherheitsneutraler Code wirkt sich nicht explizit auf das Sicherheitssystem aus. Er wird mit den jeweiligen Berechtigungen ausgeführt, die er erhält. Obwohl Anwendungen, die keine zu geschützten Operationen \(z. B. die Verwendung von Dateien, Netzwerkfunktionen usw.\) zugeordneten Sicherheitsausnahmen abfangen können, zu einer nicht behandelten Ausnahme führen können, nutzt der sicherheitsneutrale Code weiterhin die .NET Framework\-Sicherheitstechnologien.  
  
 Eine sicherheitsneutrale Bibliothek weist besondere Merkmale auf, die Sie kennen sollten. Angenommen, Ihre Bibliothek stellt API\-Elemente bereit, die Dateien verwenden oder nicht verwalteten Code aufrufen. Wenn der Code nicht über die entsprechende Berechtigung verfügt, wird er nicht wie beschrieben ausgeführt. Auch wenn der Code über die Berechtigung verfügt, muss jeder ihn aufrufende Anwendungscode über dieselbe Berechtigung verfügen, damit er funktioniert. Wenn der aufrufende Code nicht über die richtige Berechtigung verfügt, wird als Ergebnis des Stackwalk der Codezugriffssicherheit eine <xref:System.Security.SecurityException> angezeigt.  
  
## Anwendungscode, der keine wiederverwendbare Komponente darstellt  
 Wenn Ihr Code Teil einer Anwendung ist, die nicht von anderem Code aufgerufen wird, ist die Sicherheit einfach zu erreichen und möglicherweise keine spezielle Codierung erforderlich. Beachten Sie jedoch, dass Ihr Code von schädlichem Code aufgerufen werden kann. Obwohl die Codezugriffssicherheit möglicherweise den Zugriff auf Ressourcen durch schädlichen Code beenden kann, könnte dieser Code weiterhin Werte Ihrer Felder oder Eigenschaften lesen, die möglicherweise vertrauliche Informationen enthalten.  
  
 Darüber hinaus müssen Sie hinsichtlich schädlicher Eingaben vorsichtig sein, wenn Ihr Code Benutzereingaben aus dem Internet oder anderen unzuverlässigen Quellen akzeptiert.  
  
## Implementierung von verwalteten Wrappern für systemeigenen Code  
 In diesem Szenario werden in der Regel einige nützliche Funktionen in systemeigenem Code implementiert, die Sie für verwalteten Code verfügbar machen können. Verwaltete Wrapper sind mithilfe von Plattformaufrufen oder COM\-Interops einfach zu schreiben. Wenn Sie auf diese Weise vorgehen, müssen die Aufrufer der Wrapper über Berechtigungen für nicht verwalteten Code verfügen, um erfolgreich agieren zu können. Entsprechend der Standardrichtlinie bedeutet dies, dass der aus einem Intranet oder dem Internet heruntergeladene Code mit den Wrappern nicht funktioniert.  
  
 Anstatt allen Anwendungen, die diese Wrapper verwenden, die Berechtigungen für nicht verwalteten Code zu gewähren, ist es besser, diese Berechtigungen nur dem Wrappercode zuzuordnen. Wenn die zugrunde liegenden Funktionen keine Ressourcen verfügbar machen und die Implementierung entsprechend sicher ist, muss der Wrapper nur seine Rechte bestätigen, wodurch Aufrufe von beliebigem Code über den Wrapper ermöglicht werden. Wenn Ressourcen einbezogen sind, sollte die Codierung der Sicherheit mit der im Bibliothekscodefall verwendeten Codierung identisch sein, der im nächsten Abschnitt beschrieben wird. Da der Wrapper Aufrufer dieser Ressourcen potenziell verfügbar macht, ist eine sorgfältige Überprüfung der Sicherheit des systemeigenen Codes erforderlich, für die der Wrapper zuständig ist.  
  
## Bibliothekscode zur Offenlegung geschützter Ressourcen  
 Dies ist der leistungsstärkste und daher möglicherweise ein gefährlicher Ansatz \(bei falscher Durchführung\) für Sicherheitscode: Ihre Bibliothek fungiert hier als Schnittstelle für anderen Code für den Zugriff auf bestimmte Ressourcen, die anderweitig nicht verfügbar sind, ebenso wie die Klassen von .NET Framework die Berechtigungen für die Ressourcen erzwingen, die sie verwenden. Überall dort, wo Sie eine Ressource verfügbar machen, muss der Code zunächst die für die Ressource geeignete Berechtigung anfordern \(d. h. er muss eine Sicherheitsüberprüfung durchführen\) und seine Rechte dann in der Regel bestätigen, um den eigentlichen Vorgang ausführen zu können.  
  
## Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|------------------|  
|[How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)|Erläutert die Ausführung einer teilweise vertrauenswürdigen Anwendung in einer eingeschränkten Sicherheitsumgebung, die die ihr gewährten Codezugriffsberechtigungen einschränkt.|  
|[Securing State Data](../../../docs/standard/security/securing-state-data.md)|Beschreibt, wie private Member geschützt werden.|  
|[Securing Method Access](../../../docs/framework/misc/securing-method-access.md)|Beschreibt, wie Methoden vor dem Aufrufen durch teilweise vertrauenswürdigen Code geschützt werden.|  
|[Securing Wrapper Code](../../../docs/framework/misc/securing-wrapper-code.md)|Beschreibt die Sicherheitsrisiken für Code, der anderen Code umschließt.|  
|[Security and Public Read\-only Array Fields](../../../docs/framework/misc/security-and-public-read-only-array-fields.md)|Beschreibt die Sicherheitsrisiken für Code, der öffentliche schreibgeschützte Arrays in .NET Framework\-Bibliotheken verwendet.|  
|[Securing Exception Handling](../../../docs/framework/misc/securing-exception-handling.md)|Beschreibt die Sicherheitsrisiken für die Ausnahmebehandlung.|  
|[Security and User Input](../../../docs/standard/security/security-and-user-input.md)|Beschreibt die Sicherheitsrisiken für Anwendungen, die Benutzereingaben akzeptieren.|  
|[Security and Remoting Considerations](../../../docs/framework/misc/security-and-remoting-considerations.md)|Beschreibt die Sicherheitsrisiken für Anwendungen, die über verschiedene Anwendungsdomänen hinweg kommunizieren.|  
|[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)|Beschreibt die Sicherheitsrisiken bei der Serialisierung von Objekten.|  
|[Security and Race Conditions](../../../docs/standard/security/security-and-race-conditions.md)|Beschreibt, wie Racebedingungen im Code vermieden werden.|  
|[Security and On\-the\-Fly Code Generation](../../../docs/standard/security/security-and-on-the-fly-code-generation.md)|Beschreibt die Sicherheitsrisiken für Anwendungen, die dynamischen Code generieren.|  
|[Security and Setup Issues](../Topic/Security%20and%20Setup%20Issues.md)|Beschreibt Überlegungen zum Testen und Einrichten Ihrer Anwendung.|  
|[Code Access Security](../../../docs/framework/misc/code-access-security.md)|Beschreibt die .NET Framework\-Codezugriffssicherheit ausführlich und bietet Anweisungen zu deren Verwendung im Code.|  
|[Role\-Based Security](../../../docs/standard/security/role-based-security.md)|Beschreibt die rollenbasierte .NET Framework\-Sicherheit ausführlich und bietet Anweisungen zu deren Verwendung im Code.|