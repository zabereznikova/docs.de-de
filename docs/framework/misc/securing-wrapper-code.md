---
title: Sichern von Wrappercode
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], wrapper code
- wrapper code, securing
- secure coding, wrapper code
- code security, wrapper code
ms.assetid: 1df6c516-5bba-48bd-b450-1070e04b7389
author: mairaw
ms.author: mairaw
ms.openlocfilehash: abbc817142ab6906a04b4dc053693f87109922dc
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487893"
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
  
### <a name="in-version-20-and-later-versions-of-the-net-framework"></a>In Version 2.0 und höheren Versionen von .NET Framework  
 Version 2.0 und höheren Versionen von .NET Framework, führt Sicherheitsaktion für den Delegatersteller im Gegensatz zu früheren Versionen Wenn der Delegat erstellt und aufgerufen wird.  
  
- Wenn ein Delegat erstellt wird, werden Sicherheitsverknüpfungsaufrufe für die Zielmethode des Delegaten anhand der Berechtigungen des Delegaterstellers ausgeführt.  Wenn die Sicherheitsaktion nicht erfüllt werden kann, führt dies zu einer <xref:System.Security.SecurityException>.  
  
- Der Berechtigungssatz des Delegaterstellers wird auch während der Delegaterstellung erfasst und zusammen mit dem Delegaten gespeichert.  
  
- Wenn der Delegat aufgerufen wird, wird der erfasste Berechtigungssatz des Delegaterstellers zuerst anhand aller Forderungen im aktuellen Kontext ausgewertet, wenn der Delegatersteller und der Aufrufer zu unterschiedlichen Assemblys gehören.  Im nächsten Schritt werden alle vorhandenen Sicherheitsforderungen für den Delegataufrufer ausgeführt.  
  
## <a name="link-demands-and-wrappers"></a>Verknüpfungsaufrufe und Wrapper  
 In der Sicherheitsinfrastruktur wurde ein besonderer Schutzmechanismus mit Verknüpfungsaufrufen verstärkt. Dies stellt jedoch noch immer eine Quelle für potenzielle Schwachstellen in Ihrem Code dar.  
  
 Wenn vollständig vertrauenswürdiger Code eine Eigenschaft, Ereignis oder geschützte Methode aufruft. ein [LinkDemand](../../../docs/framework/misc/link-demands.md), der Aufruf erfolgreich ist, wenn die **LinkDemand** berechtigungsüberprüfung für den Aufrufer erfüllt wird. Darüber hinaus, wenn der vollständig vertrauenswürdige Code eine Klasse verfügbar gemacht hat, die den Namen einer Eigenschaft und Aufrufe der **erhalten** Accessor mithilfe von Reflektion, die zum Aufrufen der **erhalten** -Zugriffsmethode erfolgreich, obwohl der Benutzercode wird haben Sie nicht das Recht, diese Eigenschaft zuzugreifen. Grund hierfür ist die **LinkDemand** überprüft nur den unmittelbaren Aufrufer, der vollständig vertrauenswürdige Code handelt. Im Wesentlichen nimmt der vollständig vertrauenswürdige Code einen privilegierten Aufruf im Auftrag von Benutzercode vor, ohne sicherzustellen, dass der Code über die Berechtigung zum Ausführen dieses Aufrufs verfügt.  
  
 Zur Vermeidung solcher Sicherheitslücken erweitert die common Language Runtime die Überprüfung in eine vollständige stapelforderung für jeden indirekten Aufruf einer Methode, Konstruktor, Eigenschaft oder das Ereignis durch geschützte eine **LinkDemand**. Dieser Schutz geht zu Lasten der Leistung und ändert die Semantik der Sicherheitsüberprüfung. Für die vollständige Stapelforderung kann ein Fehler auftreten, der bei der schnelleren Überprüfung einer Ebene nicht auftreten würde.  
  
## <a name="assembly-loading-wrappers"></a>Wrapper zum Laden von Assemblys  
 Mehrere Methoden werden zum Laden von verwaltetem Code verwendet, z. B. <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>. Dabei werden Assemblys mit dem Beweis des Aufrufers geladen. Wenn Sie eine dieser Methoden in einen Wrapper einschließen, könnte das Sicherheitssystem die Berechtigung Ihres Codes anstelle der Berechtigungen des Aufrufers Ihres Wrappers zum Laden von Assemblys verwenden. Sie sollten nicht zulassen, dass wenig vertrauenswürdiger Code anderen Code laden kann, dem höhere Berechtigungen als dem Aufrufer Ihres Wrappers gewährt wurden.  
  
 Jeglicher Code, der eine vollständige Vertrauensstellung oder eine höhere Vertrauensstellung als ein möglicher Aufrufer (einschließlich eines Aufrufers mit Berechtigungen auf Internetebene) aufweist, kann die Sicherheit auf diese Weise herabsetzen. Wenn Ihr Code eine öffentliche Methode, die ein Bytearray annimmt und übergibt es an **Assembly.Load**, und erstellen eine Assembly, auf den Namen des Aufrufers erstellt, sie können zur funktionsunfähigkeit von Sicherheit.  
  
 Dieses Problem betrifft die folgenden API-Elemente:  
  
- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
  
## <a name="demand-vs-linkdemand"></a>"Demand" im Vergleich zu "LinkDemand"  
 Die deklarative Sicherheit stellt zwei Arten von Sicherheitsüberprüfungen bereit, die zwar ähnlich sind, jedoch sehr unterschiedliche Überprüfungen ausführen. Sie sollten beide Formen kennen, weil die falsche Auswahl zu schwacher Sicherheit oder Leistungverlusten führen kann.  
  
 Die deklarative Sicherheit bietet die folgenden Sicherheitsüberprüfungen:  
  
- <xref:System.Security.Permissions.SecurityAction.Demand> gibt den Stackwalk für die Codezugriffssicherheit an. Alle Aufrufer für den Stapel benötigen die angegebene Berechtigung oder Identität, um die Überprüfung zu bestehen. **Bei Bedarf** tritt bei jedem Aufruf, da der Stapel ggf. verschiedene Aufrufer enthält. Wenn Sie eine Methode wiederholt aufrufen, tritt diese Sicherheitsüberprüfung jedes Mal auf. **Bei Bedarf** ist ein guter Schutz vor Lockangriffen dar; nicht autorisierter Code, von dem zu durchbrechen erkannt.  
  
- [LinkDemand](../../../docs/framework/misc/link-demands.md) erfolgt zur Kompilierungszeit für just-in-Time (JIT) und nur den unmittelbaren Aufrufer überprüft. Diese Sicherheitsüberprüfung überprüft nicht den Aufrufer des Aufrufers. Nachdem diese Überprüfung erfolgreich war, werden unabhängig von der Anzahl der Aufrufe durch den Aufrufer keine weiteren Sicherheitsmaßnahmen ergriffen. Es besteht jedoch auch kein Schutz vor Lockangriffen. Mit **LinkDemand**, jeglicher Code, der den Test besteht und kann auf Ihren Code verweisen kann zu schwerwiegenden Fehlern führen Sicherheit von bösartigem Code rufen Sie mithilfe des autorisierten Codes ermöglicht. Aus diesem Grund verwenden Sie keine **LinkDemand** es sei denn, alle potenziellen Risiken ausdrücklich vermieden werden können.  
  
    > [!NOTE]
    >  In .NET Framework 4 wurden Verknüpfungsaufrufe durch ersetzt die <xref:System.Security.SecurityCriticalAttribute> -Attribut im <xref:System.Security.SecurityRuleSet.Level2> Assemblys. Die <xref:System.Security.SecurityCriticalAttribute> entspricht einem Verknüpfungsaufruf für volle Vertrauenswürdigkeit; allerdings auch auf die Vererbungsregeln angewendet. Weitere Informationen zu dieser Änderung finden Sie unter [Sicherheitstransparenter Code, Ebene 2](../../../docs/framework/misc/security-transparent-code-level-2.md).  
  
 Bei Verwendung der zusätzlichen Vorsichtsmaßnahmen **LinkDemand** müssen einzeln programmiert werden; das sicherheitssytem kann bei der Erzwingung helfen. Jeder Fehler stellt ein Sicherheitsrisiko dar. Der gesamte autorisierte Code, der Ihren Code verwendet, muss für die Implementierung zusätzlicher Sicherheit verantwortlich sein, indem die folgenden Maßnahmen ergriffen werden:  
  
- Einschränken des Zugriffs des aufrufenden Codes auf die Klasse oder Assembly.  
  
- Verwenden der gleichen Sicherheitsüberprüfungen für den aufrufenden Code, die für den Code verwendet werden, der aufgerufen wird, und Verpflichten seiner Aufrufer zu dieser Überprüfung. Z. B. Wenn Sie Code schreiben, die eine Methode aufruft, ist geschützt, mit einem **LinkDemand** für die <xref:System.Security.Permissions.SecurityPermission> mit der <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> Flag angegeben ist, stellen Sie die Methode sollte außerdem eine **LinkDemand** (oder **Bedarf**, der stärker ist) für diese Berechtigung. Die Ausnahme ist, wenn der Code verwendet die **LinkDemand**-geschützte Methode auf eingeschränkte Weise, die Sie möchten sicher ist, erhält der andere transportsicherheitsschutzmechanismen (z. B. Forderungen) in Ihrem Code. In diesem Ausnahmefall übernimmt der Aufrufer die Verantwortung für die Herabsetzung des Sicherheitsschutzes des zugrunde liegenden Codes.  
  
- Sicherstellen, dass die Aufrufer Ihres Codes den Code nicht veranlassen können, den geschützten Code in ihrem Auftrag aufzurufen. Dies bedeutet, dass Aufrufer den autorisierten Code nicht zwingen können, bestimmte Parameter an den geschützten Code zu übergeben oder Ergebnisse aus ihm abzurufen.  
  
### <a name="interfaces-and-link-demands"></a>Schnittstellen und Verknüpfungsaufrufe  
 Wenn eine virtuelle Methode, Eigenschaft oder das Ereignis mit **LinkDemand** eine Basisklassenmethode überschreibt die Basisklassenmethode müssen auch die gleichen **LinkDemand** für die überschriebene Methode, um effektiv zu sein. Es ist möglich, dass bösartiger Code eine erneute Umwandlung in den Basistyp ausführt und die Methode der Basisklasse aufruft. Beachten Sie außerdem, dass Verknüpfungsaufrufe Assemblys implizit hinzugefügt werden können, für die das Attribut <xref:System.Security.AllowPartiallyTrustedCallersAttribute> nicht auf Assemblyebene festgelegt ist.  
  
 Eine bewährte Methode besteht darin, Methodenimplementierungen durch Verknüpfungsaufrufen zu schützen, wenn Schnittstellenmethoden ebenfalls Verknüpfungsaufrufe aufweisen. Beachten Sie hinsichtlich der Verwendung von Verknüpfungsaufrufen mit Schnittstellen Folgendes:  
  
- Setzen Sie ein **LinkDemand** für eine öffentliche Methode einer Klasse, die eine Schnittstellenmethode implementiert die **LinkDemand** wird nicht erzwungen werden, wenn Sie anschließend in der Schnittstelle umgewandelt, und rufen Sie die Methode. In diesem Fall, da Sie mit der Schnittstelle nur verknüpft die **LinkDemand** für die Schnittstelle berücksichtigt wird.  
  
 Überprüfen Sie die folgenden Elemente auf Sicherheitsprobleme:  
  
- Explizite Verknüpfungsaufrufe für Schnittstellenmethoden. Stellen Sie sicher, dass diese Verknüpfungsaufrufe den erwarteten Schutz bieten. Ermitteln Sie, ob bösartiger Code mithilfe einer Umwandlung die Verknüpfungsaufrufe wie oben beschrieben umgehen kann.  
  
- Virtuelle Methoden mit angewendeten Verknüpfungsaufrufen.  
  
- Typen und Schnittstellen, die sie implementieren. Diese sollten Verknüpfungsaufrufe einheitlich verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
