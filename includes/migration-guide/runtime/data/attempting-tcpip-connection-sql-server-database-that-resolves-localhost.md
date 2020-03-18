---
ms.openlocfilehash: e36dac19beb6251debef100656670a6623344eea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "68237841"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Der Versuch, eine TCP/IP-Verbindung mit einer SQL Server-Datenbank herzustellen, die zu `localhost` aufgelöst wird, schlägt fehl

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6 und 4.6.1 tritt bei dem Versuch, eine TCP/IP-Verbindung mit einer SQL Server-Datenbank herzustellen, die zu <code>localhost</code> aufgelöst wird, folgender Fehler auf: &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server. Der Server wurde nicht gefunden, oder auf ihn kann nicht zugegriffen werden. Stellen Sie sicher, dass der Instanzname richtig und SQL Server so konfiguriert ist, das Remoteverbindungen zulässig sind. (provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified).&quot; (Beim Einrichten einer Verbindung mit SQL Server ist ein netzwerk- oder instanzenabhängiger Fehler aufgetreten. (Anbieter: SQL-Netzwerkschnittstellen, Fehler: 26 – Fehler beim Suchen des angegebenen Servers/der angegebenen Instanz.))|
|Vorschlag|Dieses Problem wurde behoben und das vorherige Verhalten in .NET Framework 4.6.2 wiederhergestellt. Führen Sie ein Upgrade auf .NET Framework 4.6.2 durch, um eine Verbindung mit einer SQL Server-Datenbank herzustellen, die zu <code>localhost</code> aufgelöst wird.|
|`Scope`|Nebenversion|
|Version|4.6|
|Geben Sie Folgendes ein:|Laufzeit|
