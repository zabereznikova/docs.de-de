---
ms.openlocfilehash: bbeca87b3f498213b91d942cc4f197c9d80457a8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496482"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Der Versuch, eine TCP/IP-Verbindung mit einer SQL Server-Datenbank herzustellen, die zu `localhost` aufgelöst wird, schlägt fehl

#### <a name="details"></a>Details

Ab .NET Framework 4.6 und 4.6.1 tritt bei dem Versuch, eine TCP/IP-Verbindung mit einer SQL Server-Datenbank herzustellen, die zu <code>localhost</code> aufgelöst wird, folgender Fehler auf: &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server. Der Server wurde nicht gefunden oder es konnte nicht auf ihn zugegriffen werden. Stellen Sie sicher, dass der Instanzname richtig und SQL Server so konfiguriert ist, das Remoteverbindungen zulässig sind. (Anbieter: SQL-Netzwerkschnittstellen, Fehler: 26 – Fehler beim Auffinden des angegebenen Servers/der angegebenen Instanz)&quot;

#### <a name="suggestion"></a>Vorschlag

Dieses Problem wurde behoben und das vorherige Verhalten in .NET Framework 4.6.2 wiederhergestellt. Führen Sie ein Upgrade auf .NET Framework 4.6.2 durch, um eine Verbindung mit einer SQL Server-Datenbank herzustellen, die zu <code>localhost</code> aufgelöst wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
