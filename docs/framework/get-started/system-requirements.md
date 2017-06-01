---
title: "Systemanforderungen für .NET Frameworks | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- software requirements
- .NET Framework, system requirements
- system requirements
- operating systems supported
- hardware requirements
ms.assetid: 298275e2-da1d-4618-9f74-6a3567832350
caps.latest.revision: 95
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: ddcefb2b35f8cbf06a3abcc16158eee850f799ff
ms.openlocfilehash: ec4594343c5a78649d7d7a4d151545612da9138b
ms.contentlocale: de-de
ms.lasthandoff: 05/11/2017

---
# <a name="net-framework-system-requirements"></a>Systemanforderungen für .NET Framework
Die Tabellen in diesem Thema enthalten die Hardware-, Betriebssystem- und Softwareanforderungen für .NET Framework 4.5 und dessen Punktreleases (4.5.1 und 4.5.2), [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und dessen Punktreleases (4.6.1 und 4.6.2) sowie .NET Framework 4.7. Für Entwicklungsumgebungen, in denen Anwendungen für das .NET Framework entwickelt werden können, gelten separate Anforderungen.

 Downloadinformationen und Links finden Sie im [Installationshandbuch](../../../docs/framework/install/guide-for-developers.md).

 Informationen zum Support Lifecycle der .NET Framework-Versionen finden Sie unter [Microsoft Support Lifecycle](https://support.microsoft.com/en-us/lifecycle/search?sort=PN&alpha=Microsoft%20.NET%20Framework&Filter=FilterNO).

## <a name="hardware-requirements"></a>Hardwareanforderungen

|||
|-|-|
|**Prozessor**|1 GHz|
|**RAM**|512 MB|
|**Speicherplatz (Minimum)**||
|32-Bit|4,5 GB|
|64-Bit|4,5 GB|

## <a name="installation-requirements"></a>Installationsanforderungen

- Für die Installation von .NET Framework sind Administratorrechte erforderlich. Wenn Sie über keine Administratorrechte für den Computer verfügen, auf dem Sie .NET Framework installieren möchten, wenden Sie sich an Ihren Netzwerkadministrator.

## <a name="supported-client-operating-systems"></a>Unterstützte Clientbetriebssysteme

|Betriebssystem|Unterstützte Editionen|Mit vorinstalliertem Betriebssystem|Separat installierbar|
|----------------------|------------------------|------------------------------|----------------------------|
| Windows 10 Creators Update|32 Bit und 64 Bit|.NET Framework 4.7|| 
|Windows 10 Anniversary Update|32 Bit und 64 Bit|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|.NET Framework 4.7|
|Windows 10-Update von November|32 Bit und 64 Bit|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]||
|Windows 10|32 Bit und 64 Bit|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
|[!INCLUDE[win81](../../../includes/win81-md.md)]|32-Bit, 64-Bit und ARM|[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]|[!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7|
|[!INCLUDE[win8](../../../includes/win8-md.md)]|32-Bit, 64-Bit und ARM|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]|[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
|Windows 7 SP1|32 Bit und 64 Bit|--|.NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|
|Windows Vista SP2|32 Bit und 64 Bit|--|.NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|
|Windows XP|32 Bit und 64 Bit|--|.NET Framework 4|

 **Hinweise:**

- Auf Windows 7-Systemen erfordert .NET Framework Windows 7 SP1. Wenn Sie mit Windows 7 arbeiten und Service Pack 1 noch nicht installiert haben, müssen Sie dies nachholen, bevor Sie .NET Framework installieren.

- [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] wird von Windows Preinstallation Environment (Windows PE) unterstützt. Windows PE unterstützt nicht alle Funktionen.

- .NET Framework 4 unterstützt auch die IA64-Plattform.

- Um bestmögliche Kompatibilität und höchste Sicherheit zu gewährleisten, wird für alle Plattformen empfohlen, ein Upgrade auf das neueste Windows Service Pack durchzuführen und wichtige Updates zu installieren, die auf der [Windows Update-Website](http://go.microsoft.com/fwlink/?LinkId=168461) verfügbar sind.

- Unter 64-Bit-Betriebssystemen unterstützt das .NET Framework sowohl WOW64 (32-Bit-Verarbeitung auf einem 64-Bit-Computer) als auch systemeigene 64-Bit-Verarbeitung.

## <a name="supported-server-operating-systems"></a>Unterstützte Serverbetriebssysteme

|Betriebssystem|Unterstützte Editionen|Mit vorinstalliertem Betriebssystem|Separat installierbar|
|----------------------|------------------------|------------------------------|----------------------------|
|Windows Server 2016|64-Bit|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|.NET Framework 4.7|
|[!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)]|64-Bit|[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]|[!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7|
|[!INCLUDE[winserver8](../../../includes/winserver8-md.md)] (64-Bit-Edition)|64-Bit|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]|[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7|
|Windows Server 2008 R2 SP1|64-Bit|--|.NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7|
|Windows Server 2008 SP2|32 Bit und 64 Bit|--|.NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|

 **Hinweise:**

- [!INCLUDE[winserver8](../../../includes/winserver8-md.md)] enthält [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], Sie müssen also keine separate Installation durchführen. [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] enthält [!INCLUDE[net_v451](../../../includes/net-v451-md.md)].

- .NET Framework wird in der Server Core-Rolle mit Windows Server 2008 R2 SP1 oder höher unterstützt, jedoch nicht unter Windows Server 2008 SP1 für Itanium-basierte Systeme.

- Unter Windows Server 2008 SP2 wird .NET Framework in der Server Core-Rolle nicht unterstützt.

- Um bestmögliche Kompatibilität und höchste Sicherheit zu gewährleisten, wird für alle Plattformen empfohlen, ein Upgrade auf das neueste Windows Service Pack durchzuführen und wichtige Updates zu installieren, die auf der [Windows Update-Website](http://go.microsoft.com/fwlink/?LinkId=168461) verfügbar sind. Die Installation des neuesten Windows Service Pack ist möglicherweise unter einigen Betriebssystemen erforderlich.

- Unter 64-Bit-Betriebssystemen unterstützt das .NET Framework sowohl WOW64 (32-Bit-Verarbeitung auf einem 64-Bit-Computer) als auch systemeigene 64-Bit-Verarbeitung.

## <a name="see-also"></a>Siehe auch
 [Installationshandbuch](../../../docs/framework/install/guide-for-developers.md)   
 [Getting Started (Erste Schritte)](../../../docs/framework/get-started/index.md)   
 [Problembehandlung](../../../docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)
