---
ms.openlocfilehash: bbeca87b3f498213b91d942cc4f197c9d80457a8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496482"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a><span data-ttu-id="4b475-101">Der Versuch, eine TCP/IP-Verbindung mit einer SQL Server-Datenbank herzustellen, die zu `localhost` aufgelöst wird, schlägt fehl</span><span class="sxs-lookup"><span data-stu-id="4b475-101">Attempting a TCP/IP connection to a SQL Server database that resolves to `localhost` fails</span></span>

#### <a name="details"></a><span data-ttu-id="4b475-102">Details</span><span class="sxs-lookup"><span data-stu-id="4b475-102">Details</span></span>

<span data-ttu-id="4b475-103">Ab .NET Framework 4.6 und 4.6.1 tritt bei dem Versuch, eine TCP/IP-Verbindung mit einer SQL Server-Datenbank herzustellen, die zu <code>localhost</code> aufgelöst wird, folgender Fehler auf: &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4b475-103">In the .NET Framework 4.6 and 4.6.1, attempting a TCP/IP connection to a SQL Server database that resolves to <code>localhost</code> fails with the error, &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span></span> <span data-ttu-id="4b475-104">Der Server wurde nicht gefunden oder es konnte nicht auf ihn zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="4b475-104">The server was not found or was not accessible.</span></span> <span data-ttu-id="4b475-105">Stellen Sie sicher, dass der Instanzname richtig und SQL Server so konfiguriert ist, das Remoteverbindungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="4b475-105">Verify that the instance name is correct and that SQL Server is configured to allow remote connections.</span></span> <span data-ttu-id="4b475-106">(Anbieter: SQL-Netzwerkschnittstellen, Fehler: 26 – Fehler beim Auffinden des angegebenen Servers/der angegebenen Instanz)&quot;</span><span class="sxs-lookup"><span data-stu-id="4b475-106">(provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified)&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4b475-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="4b475-107">Suggestion</span></span>

<span data-ttu-id="4b475-108">Dieses Problem wurde behoben und das vorherige Verhalten in .NET Framework 4.6.2 wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="4b475-108">This issue has been addressed and the previous behavior restored in the .NET Framework 4.6.2.</span></span> <span data-ttu-id="4b475-109">Führen Sie ein Upgrade auf .NET Framework 4.6.2 durch, um eine Verbindung mit einer SQL Server-Datenbank herzustellen, die zu <code>localhost</code> aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="4b475-109">To connect to a SQL Server database that resolves to <code>localhost</code>, upgrade to the .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="4b475-110">name</span><span class="sxs-lookup"><span data-stu-id="4b475-110">Name</span></span>    | <span data-ttu-id="4b475-111">Wert</span><span class="sxs-lookup"><span data-stu-id="4b475-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4b475-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="4b475-112">Scope</span></span>   |<span data-ttu-id="4b475-113">Gering</span><span class="sxs-lookup"><span data-stu-id="4b475-113">Minor</span></span>|
|<span data-ttu-id="4b475-114">Version</span><span class="sxs-lookup"><span data-stu-id="4b475-114">Version</span></span>|<span data-ttu-id="4b475-115">4.6</span><span class="sxs-lookup"><span data-stu-id="4b475-115">4.6</span></span>|
|<span data-ttu-id="4b475-116">Typ</span><span class="sxs-lookup"><span data-stu-id="4b475-116">Type</span></span>|<span data-ttu-id="4b475-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="4b475-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4b475-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4b475-118">Affected APIs</span></span>

<span data-ttu-id="4b475-119">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="4b475-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
