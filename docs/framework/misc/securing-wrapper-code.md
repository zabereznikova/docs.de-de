---
title: Sichern von Wrappercode
description: Informieren Sie sich über das Sichern von Wrapper Code, der einen eindeutigen Satz von Sicherheitslücken eröffnen kann, insbesondere dann, wenn der Wrapper eine höhere Vertrauensstellung als der Code verwendet, der ihn verwendet.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], wrapper code
- wrapper code, securing
- secure coding, wrapper code
- code security, wrapper code
ms.assetid: 1df6c516-5bba-48bd-b450-1070e04b7389
ms.openlocfilehash: 64c5b2455882ca121a6eeb0c0bbcbc4d04ed88cd
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281445"
---
# <a name="securing-wrapper-code"></a>Sichern von Wrappercode
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Wrappercode kann vor allem dann, wenn der Wrapper eine höhere Vertrauensstellung als Code besitzt, der ihn verwendet, einen eindeutigen Satz von Sicherheitsrisiken eröffnen. Alle Aktionen, die im Auftrag eines Aufrufers vorgenommen werden, bei denen die eingeschränkten Berechtigungen des Aufrufers nicht in der entsprechenden Sicherheitsüberprüfung enthalten sind, stellen eine potenzielle Schwachstelle dar, die ausgenutzt werden kann.  
  
 Aktivieren Sie niemals Aktionen über den Wrapper, die der Aufrufer nicht selbst ausführen könnte. Dies ist besonders riskant, wenn Aktionen ausgeführt werden, die eine eingeschränkte Sicherheitsüberprüfung im Gegensatz zu einer vollständigen Stapelanforderung beinhalten. Wenn Überprüfungen einer Ebene ausgeführt werden, kann das Einfügen des Wrappercodes zwischen dem tatsächlichen Aufrufer und dem betreffenden API-Element leicht bewirken, dass die Sicherheitsüberprüfung erfolgreich ist, obwohl sie es nicht sein sollte. Auf diese Weise wird die Sicherheit geschwächt.  
  
## <a name="delegates"></a>Delegaten  
 Die Delegatsicherheit unterscheidet sich in den verschiedenen Versionen von .NET Framework.  Dieser Abschnitt beschreibt das verschiedene Delegatverhalten und die damit verbundenen Sicherheitsüberlegungen.  
  
### <a name="in-version-10-and-11-of-the-net-framework"></a>In Version 1.0 und 1.1 von .NET Framework  
 Die Versionen 1.0 und 1.1 von .NET Framework führen die folgenden Sicherheitsaktionen für einen Delegatersteller und einen Delegataufrufer aus.  
  
- Wenn ein Delegat erstellt wird, werden Sicherheitsverknüpfungsaufrufe für die Zielmethode des Delegaten anhand der Berechtigungen des Delegaterstellers ausgeführt.  Wenn die Sicherheitsaktion nicht erfüllt werden kann, führt dies zu einer <xref:System.Security.SecurityException>.  
  
- Wenn der Delegat aufgerufen wird, werden alle vorhandenen Sicherheitsforderungen für den Delegataufrufer ausgeführt.  
  
 Jedes Mal, wenn der Code einen <xref:System.Delegate> von weniger vertrauenswürdigem Code annimmt, der ihn aufrufen kann, müssen Sie sicherstellen, dass Sie den weniger vertrauenswürdigen Code nicht ermöglichen, seine Berechtigungen auszuweiten. Wenn Sie einen Delegaten annehmen und später verwenden, befindet sich der Code, der den Delegaten erstellt hat, nicht in der Aufrufliste, und seine Berechtigungen werden nicht getestet, wenn Code in oder unter dem Delegaten versucht, einen geschützten Vorgang auszuführen. Wenn Ihr Code und und der Aufrufercode über höhere Berechtigungen als der Ersteller verfügen, kann der Ersteller den Aufrufpfad orchestrieren, ohne Teil der Aufrufliste zu sein.  
  
### <a name="in-version-20-and-later-versions-of-the-net-framework"></a>In Version 2,0 und höheren Versionen der .NET Framework  
 Im Gegensatz zu früheren Versionen werden von Version 2,0 und höheren Versionen der .NET Framework Sicherheitsmaßnahmen gegen den Delegatersteller ausgeführt, wenn der Delegat erstellt und aufgerufen wird.  
  
- Wenn ein Delegat erstellt wird, werden Sicherheitsverknüpfungsaufrufe für die Zielmethode des Delegaten anhand der Berechtigungen des Delegaterstellers ausgeführt.  Wenn die Sicherheitsaktion nicht erfüllt werden kann, führt dies zu einer <xref:System.Security.SecurityException>.  
  
- Der Berechtigungssatz des Delegaterstellers wird auch während der Delegaterstellung erfasst und zusammen mit dem Delegaten gespeichert.  
  
- Wenn der Delegat aufgerufen wird, wird der erfasste Berechtigungssatz des Delegaterstellers zuerst anhand aller Forderungen im aktuellen Kontext ausgewertet, wenn der Delegatersteller und der Aufrufer zu unterschiedlichen Assemblys gehören.  Im nächsten Schritt werden alle vorhandenen Sicherheitsforderungen für den Delegataufrufer ausgeführt.  
  
## <a name="link-demands-and-wrappers"></a>Verknüpfungsaufrufe und Wrapper  
 In der Sicherheitsinfrastruktur wurde ein besonderer Schutzmechanismus mit Verknüpfungsaufrufen verstärkt. Dies stellt jedoch noch immer eine Quelle für potenzielle Schwachstellen in Ihrem Code dar.  
  
 Wenn voll vertrauenswürdiger Code eine Eigenschaft, ein Ereignis oder eine Methode aufruft, die durch [LinkDemand](link-demands.md)geschützt ist, wird der Aufruf erfolgreich ausgeführt, wenn die **LinkDemand** -Berechtigungsüberprüfung für den Aufrufer erfüllt ist. Wenn der vollständig vertrauenswürdige Code eine Klasse verfügbar macht, die den Namen einer Eigenschaft annimmt und deren **Get** -Zugriffsmethode mithilfe von Reflektion aufruft, ist der Aufruf des **Get** -Accessors auch dann erfolgreich, wenn der Benutzercode nicht über das Recht für den Zugriff auf diese Eigenschaft verfügt. Dies liegt daran, dass **LinkDemand** nur den unmittelbaren Aufrufer prüft, der voll vertrauenswürdiger Code ist. Im Wesentlichen nimmt der vollständig vertrauenswürdige Code einen privilegierten Aufruf im Auftrag von Benutzercode vor, ohne sicherzustellen, dass der Code über die Berechtigung zum Ausführen dieses Aufrufs verfügt.  
  
 Um derartige Sicherheitslücken zu vermeiden, erweitert das Common Language Runtime die Überprüfung auf einen vollständigen Stapel Abruf bei jedem indirekten Aufruf einer Methode, eines Konstruktors, einer Eigenschaft oder eines Ereignisses, das durch einen **LinkDemand**geschützt wird. Dieser Schutz geht zu Lasten der Leistung und ändert die Semantik der Sicherheitsüberprüfung. Für die vollständige Stapelforderung kann ein Fehler auftreten, der bei der schnelleren Überprüfung einer Ebene nicht auftreten würde.  
  
## <a name="assembly-loading-wrappers"></a>Wrapper zum Laden von Assemblys  
 Mehrere Methoden werden zum Laden von verwaltetem Code verwendet, z. B. <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>. Dabei werden Assemblys mit dem Beweis des Aufrufers geladen. Wenn Sie eine dieser Methoden in einen Wrapper einschließen, könnte das Sicherheitssystem die Berechtigung Ihres Codes anstelle der Berechtigungen des Aufrufers Ihres Wrappers zum Laden von Assemblys verwenden. Sie sollten nicht zulassen, dass wenig vertrauenswürdiger Code anderen Code laden kann, dem höhere Berechtigungen als dem Aufrufer Ihres Wrappers gewährt wurden.  
  
 Jeglicher Code, der eine vollständige Vertrauensstellung oder eine höhere Vertrauensstellung als ein möglicher Aufrufer (einschließlich eines Aufrufers mit Berechtigungen auf Internetebene) aufweist, kann die Sicherheit auf diese Weise herabsetzen. Wenn Ihr Code über eine öffentliche Methode verfügt, die ein Bytearray annimmt und es an **Assembly. Load**übergibt und dadurch eine Assembly im Auftrag des Aufrufers erstellt, kann dies die Sicherheit unterbrechen.  
  
 Dieses Problem betrifft die folgenden API-Elemente:  
  
- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
  
## <a name="demand-vs-linkdemand"></a>"Demand" im Vergleich zu "LinkDemand"  
 Die deklarative Sicherheit stellt zwei Arten von Sicherheitsüberprüfungen bereit, die zwar ähnlich sind, jedoch sehr unterschiedliche Überprüfungen ausführen. Sie sollten beide Formen kennen, weil die falsche Auswahl zu schwacher Sicherheit oder Leistungverlusten führen kann.  
  
 Die deklarative Sicherheit bietet die folgenden Sicherheitsüberprüfungen:  
  
- <xref:System.Security.Permissions.SecurityAction.Demand> gibt den Stackwalk für die Codezugriffssicherheit an. Alle Aufrufer für den Stapel benötigen die angegebene Berechtigung oder Identität, um die Überprüfung zu bestehen. Die **Nachfrage** erfolgt bei jedem Aufruf, da der Stapel möglicherweise unterschiedliche Aufrufer enthält. Wenn Sie eine Methode wiederholt aufrufen, tritt diese Sicherheitsüberprüfung jedes Mal auf. Die **Nachfrage** ist ein guter Schutz vor Lock Angriffen. nicht autorisierter Code, der versucht, ihn zu durchlaufen, wird erkannt.  
  
- [LinkDemand](link-demands.md) erfolgt zum Zeitpunkt der JIT-Kompilierung (Just-in-Time) und überprüft nur den unmittelbaren Aufrufer. Diese Sicherheitsüberprüfung überprüft nicht den Aufrufer des Aufrufers. Nachdem diese Überprüfung erfolgreich war, werden unabhängig von der Anzahl der Aufrufe durch den Aufrufer keine weiteren Sicherheitsmaßnahmen ergriffen. Es besteht jedoch auch kein Schutz vor Lockangriffen. Mit **LinkDemand**kann jeder Code, der den Test übergibt und auf den Code verweist, die Sicherheit beeinträchtigen, da bösartiger Code mithilfe des autorisierten Codes aufgerufen werden kann. Verwenden Sie daher nicht **LinkDemand** , es sei denn, alle möglichen Schwächen können gründlich vermieden werden.  
  
    > [!NOTE]
    > In den .NET Framework 4 wurden Link Aufrufe durch das-Attribut in Assemblys ersetzt <xref:System.Security.SecurityCriticalAttribute> <xref:System.Security.SecurityRuleSet.Level2> . <xref:System.Security.SecurityCriticalAttribute>Entspricht einem Link Aufruf für volle Vertrauenswürdigkeit, wirkt sich aber auch auf Vererbungs Regeln aus. Weitere Informationen zu dieser Änderung finden Sie unter [Sicherheits transparenter Code, Ebene 2](security-transparent-code-level-2.md).  
  
 Die zusätzlichen Vorkehrungen, die bei der Verwendung von **LinkDemand** erforderlich sind, müssen einzeln programmiert werden. das Sicherheitssystem kann bei der Erzwingung helfen. Jeder Fehler stellt ein Sicherheitsrisiko dar. Der gesamte autorisierte Code, der Ihren Code verwendet, muss für die Implementierung zusätzlicher Sicherheit verantwortlich sein, indem die folgenden Maßnahmen ergriffen werden:  
  
- Einschränken des Zugriffs des aufrufenden Codes auf die Klasse oder Assembly.  
  
- Verwenden der gleichen Sicherheitsüberprüfungen für den aufrufenden Code, die für den Code verwendet werden, der aufgerufen wird, und Verpflichten seiner Aufrufer zu dieser Überprüfung. Wenn Sie z. b. Code schreiben, der eine Methode aufruft, die mit einem **LinkDemand** für die <xref:System.Security.Permissions.SecurityPermission> mit dem <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> angegebenen Flag geschützt ist, sollte Ihre Methode für diese Berechtigung auch einen **LinkDemand** (oder eine höhere **Nachfrage**) erstellen. Die Ausnahme ist, wenn Ihr Code die von **LinkDemand**geschützte Methode auf eingeschränkte Weise verwendet, die Sie als sicher festlegen, wenn andere Sicherheitsmechanismen (z. b. Anforderungen) in Ihrem Code verwendet werden. In diesem Ausnahmefall übernimmt der Aufrufer die Verantwortung für die Herabsetzung des Sicherheitsschutzes des zugrunde liegenden Codes.  
  
- Sicherstellen, dass die Aufrufer Ihres Codes den Code nicht veranlassen können, den geschützten Code in ihrem Auftrag aufzurufen. Dies bedeutet, dass Aufrufer den autorisierten Code nicht zwingen können, bestimmte Parameter an den geschützten Code zu übergeben oder Ergebnisse aus ihm abzurufen.  
  
### <a name="interfaces-and-link-demands"></a>Schnittstellen und Verknüpfungsaufrufe  
 Wenn eine virtuelle Methode, eine Eigenschaft oder ein Ereignis mit **LinkDemand** eine Basisklassen Methode überschreibt, muss die Basisklassen Methode auch denselben **LinkDemand** für die überschriebene Methode aufweisen, damit Sie wirksam ist. Es ist möglich, dass bösartiger Code eine erneute Umwandlung in den Basistyp ausführt und die Methode der Basisklasse aufruft. Beachten Sie außerdem, dass Verknüpfungsaufrufe Assemblys implizit hinzugefügt werden können, für die das Attribut <xref:System.Security.AllowPartiallyTrustedCallersAttribute> nicht auf Assemblyebene festgelegt ist.  
  
 Eine bewährte Methode besteht darin, Methodenimplementierungen durch Verknüpfungsaufrufen zu schützen, wenn Schnittstellenmethoden ebenfalls Verknüpfungsaufrufe aufweisen. Beachten Sie hinsichtlich der Verwendung von Verknüpfungsaufrufen mit Schnittstellen Folgendes:  
  
- Wenn Sie einen **LinkDemand** in einer öffentlichen Methode einer Klasse platzieren, die eine Schnittstellen Methode implementiert, wird der **LinkDemand** nicht erzwungen, wenn Sie dann eine Umwandlung in die-Schnittstelle durchführt und die-Methode aufruft. Da Sie in diesem Fall mit der-Schnittstelle verknüpft sind, wird nur der **LinkDemand** in der Schnittstelle berücksichtigt.  
  
 Überprüfen Sie die folgenden Elemente auf Sicherheitsprobleme:  
  
- Explizite Verknüpfungsaufrufe für Schnittstellenmethoden. Stellen Sie sicher, dass diese Verknüpfungsaufrufe den erwarteten Schutz bieten. Ermitteln Sie, ob bösartiger Code mithilfe einer Umwandlung die Verknüpfungsaufrufe wie oben beschrieben umgehen kann.  
  
- Virtuelle Methoden mit angewendeten Verknüpfungsaufrufen.  
  
- Typen und Schnittstellen, die sie implementieren. Diese sollten Verknüpfungsaufrufe einheitlich verwenden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Richtlinien für das Schreiben von sicherem Code](../../standard/security/secure-coding-guidelines.md)
