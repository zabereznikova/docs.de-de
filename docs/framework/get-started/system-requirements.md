---
title: Systemanforderungen für .NET Framework
description: Finden Sie heraus, was die Anforderungen der Hardware, des Betriebssystems und der Software sind, um .NET Framework 4.5 und höhere Versionen zu installieren.
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- software requirements
- .NET Framework, system requirements
- system requirements
- operating systems supported
- hardware requirements
ms.assetid: 298275e2-da1d-4618-9f74-6a3567832350
ms.openlocfilehash: f853663bef4dd0de7ac61e706dedf8c6a19b5b51
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545011"
---
# <a name="net-framework-system-requirements"></a>Systemanforderungen für .NET Framework

Die Tabellen in diesem Thema enthalten die Hardware-, Betriebssystem- und Softwareanforderungen für die folgenden .NET Framework-Versionen:

- .NET Framework 4.5 und dessen Punktversionen (4.5.1 und 4.5.2).
- .NET Framework 4.6 und dessen Punktversionen (4.6.1 und 4.6.2).
- .NET Framework 4.7 und dessen Punktversionen (4.7.1 und 4.7.2).
- .NET Framework 4.8

Weitere Informationen zu .NET Framework-Versionen vor .NET Framework 4.5 finden Sie unter [.NET Framework-Versionen und-Abhängigkeiten](../migration-guide/versions-and-dependencies.md).

Für Entwicklungsumgebungen, in denen Apps für das .NET Framework entwickelt werden können, gelten separate Anforderungen.

[!INCLUDE[net-framework-4-versions](../../../includes/net-framework-4x-versions.md)]

Downloadinformationen und Links finden Sie unter [Installieren von.NET Framework für Entwickler](../install/guide-for-developers.md).

Informationen zum Support Lifecycle der .NET Framework-Versionen finden Sie unter [Microsoft Support Lifecycle](https://support.microsoft.com/lifecycle/search?sort=PN&alpha=Microsoft%20.NET%20Framework&Filter=FilterNO).

## <a name="hardware-requirements"></a>Hardwareanforderungen

|                          |        |
| ------------------------ | ------ |
| **Prozessor**            | 1 GHz  |
| **RAM**                  | 512 MB |
| **Speicherplatz (Minimum)** |        |
| 32-Bit                   | 4,5 GB |
| 64-Bit                   | 4,5 GB |

## <a name="installation-requirements"></a>Installationsanforderungen

Für die Installation von .NET Framework sind Administratorrechte erforderlich. Wenn Sie über keine Administratorrechte für den Computer verfügen, auf dem Sie .NET Framework installieren möchten, wenden Sie sich an Ihren Netzwerkadministrator.

## <a name="supported-client-operating-systems"></a>Unterstützte Clientbetriebssysteme

| Betriebssystem | Unterstützte Editionen | Mit vorinstalliertem Betriebssystem | Separat installierbar |
| ---------------- | ------------------ | ------------------------ | ---------------------- |
| Windows 10-Update von Mai 2019 | 32 Bit und 64 Bit | .NET Framework 4.8 | -- |
| Windows 10-Update von Oktober 2018 | 32 Bit und 64 Bit | .NET Framework 4.7.2 | .NET Framework 4.8 |
| Windows 10-Update vom April 2018 | 32 Bit und 64 Bit | .NET Framework 4.7.2 |.NET Framework 4.8|
| Windows 10 Fall Creators Update | 32 Bit und 64 Bit | .NET Framework 4.7.1 | .NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows 10 Creators Update | 32 Bit und 64 Bit | .NET Framework 4.7 | .NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows 10 Anniversary Update | 32 Bit und 64 Bit | .NET Framework 4.6.2 |.NET Framework 4.7<br/><br/>.NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8  |
| Windows 10-Update von November | 32 Bit und 64 Bit | .NET Framework 4.6.1 | .NET Framework 4.6.2 |
| Windows 10 | 32 Bit und 64 Bit | .NET Framework 4.6 | .NET Framework 4.6.1 <br/><br/> .NET Framework 4.6.2 |
| Windows 8.1 | 32-Bit, 64-Bit und ARM | .NET Framework 4.5.1 | .NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1<br /><br /> .NET Framework 4.6.2<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows 8 | 32-Bit, 64-Bit und ARM | .NET Framework 4.5 | .NET Framework 4.5.1<br /><br />.NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1 |
| Windows 7 SP1|32 Bit und 64 Bit | -- | .NET Framework 4<br /><br /> .NET Framework 4.5<br /><br /> .NET Framework 4.5.1<br /><br /> .NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1<br /><br /> .NET Framework 4.6.2<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows Vista SP2|32 Bit und 64 Bit | -- | .NET Framework 4<br /><br /> .NET Framework 4.5<br /><br /> .NET Framework 4.5.1<br /><br /> .NET Framework 4.5.2<br /><br /> .NET Framework 4.6 |
| Windows XP |32 Bit und 64 Bit | -- | .NET Framework 4 |

 **Hinweise:**

- Auf Windows 7-Systemen erfordert .NET Framework Windows 7 SP1. Wenn Sie mit Windows 7 arbeiten und Service Pack 1 noch nicht installiert haben, müssen Sie dies nachholen, bevor Sie .NET Framework installieren.

- .NET Framework 4.5 wird in der Windows Preinstallation Environment (Windows PE) unterstützt. Windows PE unterstützt nicht alle Funktionen.

- .NET Framework 4 unterstützt auch die IA64-Plattform.

- Um bestmögliche Kompatibilität und höchste Sicherheit zu gewährleisten, wird für alle Plattformen empfohlen, ein Upgrade auf das neueste Windows Service Pack durchzuführen und wichtige Updates zu installieren, die auf [Windows Update](https://support.microsoft.com/help/12373/windows-update-faq) verfügbar sind.

- Unter 64-Bit-Betriebssystemen unterstützt das .NET Framework sowohl WOW64 (32-Bit-Verarbeitung auf einem 64-Bit-Computer) als auch systemeigene 64-Bit-Verarbeitung.

## <a name="supported-server-operating-systems"></a>Unterstützte Serverbetriebssysteme

| Betriebssystem | Unterstützte Editionen | Mit vorinstalliertem Betriebssystem | Separat installierbar |
| ---------------- | ------------------ | ------------------------ | ---------------------- |
| Windows Server 2019 | 64-Bit | .NET Framework 4.7.2 | .NET Framework 4.8 |
| Windows Server, Version 1809 | 64-Bit | .NET Framework 4.7.2 | .NET Framework 4.8 |
| Windows Server Version 1803 | 64-Bit | .NET Framework 4.7.2 | .NET Framework 4.8 |
| Windows Server, Version 1709 | 64-Bit | .NET Framework 4.7.1 | .NET Framework 4.7.2|
| Windows Server 2016 | 64-Bit | .NET Framework 4.6.2 | .NET Framework 4.7<br/><br/> .NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows Server 2012 R2 | 64-Bit | .NET Framework 4.5.1 | .NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1<br /><br /> .NET Framework 4.6.2<br /><br />.NET Framework 4.7<br/><br/> .NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows Server 2012 (64-Bit-Edition) | 64-Bit| .NET Framework 4.5 | .NET Framework 4.5.1<br /><br /> .NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1<br /><br /> .NET Framework 4.6.2<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows Server 2008 R2 SP1|64-Bit | -- | .NET Framework 4<br /><br /> .NET Framework 4.5<br /><br /> .NET Framework 4.5.1<br /><br /> .NET Framework 4.5.2<br /><br /> .NET Framework 4.6<br /><br /> .NET Framework 4.6.1<br /><br /> .NET Framework 4.6.2<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1<br/><br/>.NET Framework 4.7.2<br/><br/>.NET Framework 4.8 |
| Windows Server 2008 SP2|32 Bit und 64 Bit | -- | .NET Framework 4<br /><br /> .NET Framework 4.5<br /><br /> .NET Framework 4.5.1<br /><br /> .NET Framework 4.5.2<br /><br /> .NET Framework 4.6 |

 **Hinweise:**

- Windows Server 2012 enthält .NET Framework 4.5, Sie müssen also keine separate Installation durchführen. Analog dazu umfasst Windows Server 2012 R2 .NET Framework 4.5.1.

- .NET Framework bietet unter Windows Server 2008 R2 SP1 oder höher eingeschränkte Unterstützung für die Server Core-Rolle. Eine Liste der nicht unterstützten APIs finden Sie im Artikel zur [Server Core .NET-Funktionalität](https://docs.microsoft.com/previous-versions//dd745015(v=vs.85)).

- .NET Framework wird unter Windows Server 2008 R2 für Itanium-basierte Systeme nicht unterstützt.

- Unter Windows Server 2008 SP2 wird .NET Framework in der Server Core-Rolle nicht unterstützt.

- Um bestmögliche Kompatibilität und höchste Sicherheit zu gewährleisten, wird für alle Plattformen empfohlen, ein Upgrade auf das neueste Windows Service Pack und wichtige Updates durchzuführen, die auf [Windows Update](https://support.microsoft.com/help/12373/windows-update-faq) verfügbar sind. Die Installation des neuesten Windows Service Pack ist möglicherweise unter einigen Betriebssystemen erforderlich.

- Unter 64-Bit-Betriebssystemen unterstützt das .NET Framework sowohl WOW64 (32-Bit-Verarbeitung auf einem 64-Bit-Computer) als auch systemeigene 64-Bit-Verarbeitung.

## <a name="see-also"></a>Siehe auch

- [Installationshandbuch](../install/index.md)
- [Erste Schritte](index.md)
- [Problembehandlung bei blockierten Installationen und Deinstallationen von .NET Framework](../install/troubleshoot-blocked-installations-and-uninstallations.md)
