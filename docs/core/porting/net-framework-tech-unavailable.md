---
title: .NET Framework-Technologien, die auf .NET Core nicht verfügbar sind
titleSuffix: ''
description: Erfahren Sie mehr über .NET Framework-Technologien, die in .NET Core nicht verfügbar sind
author: cartermp
ms.date: 04/30/2019
ms.openlocfilehash: b75d946b9436b1075a068494b941fbdea5970e42
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795598"
---
# <a name="net-framework-technologies-unavailable-on-net-core"></a>.NET Framework-Technologien, die auf .NET Core nicht verfügbar sind

Einige Technologien, die für .NET Framework-Bibliotheken verfügbar sind, sind für die Verwendung mit .NET Core nicht verfügbar, z. B. AppDomains, Remoting, Codezugriffssicherheit (Code Access Security, CAS), Sicherheitstransparenz und System.EnterpriseServices. Wenn Ihre Bibliotheken eine oder mehrere dieser Technologien benötigen, sollten Sie die unten beschriebenen alternativen Ansätze in Erwägung ziehen. Weitere Informationen zur API-Kompatibilität finden Sie unter [Breaking Changes in .NET Core](../compatibility/breaking-changes.md).

Nur weil eine API oder Technologie derzeit nicht implementiert ist, bedeutet dies nicht zwangsläufig, dass sie absichtlich nicht unterstützt wird. Durchsuchen Sie die GitHub-Repositorys nach .NET Core, um zu ermitteln, ob ein bestimmtes aufgetretenes Problem entwurfsbedingt ist. Wenn Sie einen solchen Indikator nicht finden, können Sie im [Repository dotnet/runtime](https://github.com/dotnet/runtime/issues) ein Problem melden und Fragen zu bestimmten APIs und Technologien stellen.

## <a name="appdomains"></a>AppDomains

Anwendungsdomänen (AppDomains) isolieren Apps voneinander. AppDomains benötigen eine Runtimeunterstützung und sind im Allgemeinen teuer. Das Erstellen zusätzlicher App-Domänen wird nicht unterstützt, und es ist nicht geplant, diese Funktion in Zukunft hinzuzufügen. Für Codeisolierung verwenden Sie separate Prozesse oder Container als Alternative. Verwenden Sie zum dynamischen Laden von Assemblys die <xref:System.Runtime.Loader.AssemblyLoadContext>-Klasse.

Zur Vereinfachung der Codemigration von .NET Framework stellt .NET Core einiges der <xref:System.AppDomain>-API-Oberfläche zur Verfügung. Manche Elemente der APIs funktionieren normal (z.B. <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), einige Member führen keine Aktion aus (z.B. <xref:System.AppDomain.SetCachePath%2A>), und einige davon lösen <xref:System.PlatformNotSupportedException> aus (z.B. <xref:System.AppDomain.CreateDomain%2A>). Überprüfen Sie die Typen, die Sie verwenden, anhand der [`System.AppDomain`-Referenzquelle](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Private.CoreLib/src/System/AppDomain.cs) im [GitHub-Repository „dotnet/runtime“](https://github.com/dotnet/runtime). Stellen Sie sicher, dass Sie den Branch auswählen, der ihrer implementierten Version entspricht.

## <a name="remoting"></a>Remoting

.NET-Remoting wurde als eine problematische Architektur identifiziert. Es wird für die AppDomain-übergreifende Kommunikation verwendet, die nicht mehr unterstützt wird. Darüber hinaus erfordert Remoting die Runtimeunterstützung, die teuer in der Wartung ist. Aus diesen Gründen wird .NET-Remoting auf .NET Core nicht unterstützt, und wir planen nicht, zukünftig eine Unterstützung dafür hinzuzufügen.

Für die Kommunikation zwischen Prozessen sollten Sie die Mechanismen der prozessübergreifenden Kommunikation (Inter-Process Communication, IPC) als Alternative zu Remoting berücksichtigen, z. B. die Klassen <xref:System.IO.Pipes> oder <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>.

Verwenden Sie computerübergreifend eine netzwerkbasierte Lösung als Alternative. Verwenden Sie vorzugsweise ein Nur-Text-Protokoll mit geringem Verwaltungsaufwand, z.B. HTTP. Der [Kestrel Webserver](/aspnet/core/fundamentals/servers/kestrel), der von ASP.NET Core verwendete Webserver, ist hier eine Option. Ziehen Sie auch die Verwendung von <xref:System.Net.Sockets> für netzwerkbasierte, computerübergreifende Szenarien in Erwägung. Weitere Optionen finden Sie unter [.NET Open Source Developer Projects: Messaging (.NET Open Source-Entwicklerprojekte: Messaging)](https://github.com/Microsoft/dotnet/blob/master/dotnet-developer-projects.md#messaging).

## <a name="code-access-security-cas"></a>Codezugriffssicherheit (Code Access Security, CAS)

Das Verwenden einer Sandbox, das sich auf die Runtime oder das Framework verlässt, um einzuschränken, welche Ressourcen eine verwaltete Anwendung oder Bibliothek verwendet oder ausführt, [wird in .NET Framework nicht unterstützt](../../framework/misc/code-access-security.md). Daher wird es auch in .NET Core nicht unterstützt. Es gibt zu viele Fälle im .NET Framework und in der Runtime, in denen eine Rechteerweiterung auftritt, damit CAS weiterhin als Sicherheitsgrenze behandelt wird. Darüber hinaus macht CAS die Implementierung komplizierter und führt oft zu Auswirkungen auf die Leistung der Korrektheitsprüfung für Anwendungen, die dies nicht verwenden sollen.

Verwenden Sie vom Betriebssystem bereitgestellte Sicherheitsgrenzen, wie Virtualisierung, Container oder Benutzerkonten zum Ausführen von Prozessen mit den geringstmöglichen Berechtigungen.

## <a name="security-transparency"></a>Sicherheitstransparenz

Ähnlich wie CAS trennt die Sicherheitstransparenz den Sandboxcode von sicherheitsrelevantem Code in einer deklarativen Weise, aber sie wird [nicht mehr als Sicherheitsgrenze unterstützt](../../framework/misc/security-transparent-code.md). Diese Funktion wird oft von Silverlight verwendet.

Verwenden Sie vom Betriebssystem bereitgestellte Sicherheitsgrenzen, wie Virtualisierung, Container oder Benutzerkonten zum Ausführen von Prozessen mit den geringstmöglichen Berechtigungen.

## <a name="systementerpriseservices"></a>System.EnterpriseServices

System.EnterpriseServices (COM+) wird von .NET Core nicht unterstützt.

## <a name="see-also"></a>Siehe auch

- [Übersicht über das Portieren von .NET Framework zu .NET Core](index.md)
