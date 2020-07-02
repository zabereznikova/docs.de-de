---
ms.openlocfilehash: 87cb2570d3d47a2acb85b5557141c0fef885516a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621794"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a><span data-ttu-id="1fed5-101">Der Versuch, eine TCP/IP-Verbindung mit einer SQL Server-Datenbank herzustellen, die zu `localhost` aufgelöst wird, schlägt fehl</span><span class="sxs-lookup"><span data-stu-id="1fed5-101">Attempting a TCP/IP connection to a SQL Server database that resolves to `localhost` fails</span></span>

#### <a name="details"></a><span data-ttu-id="1fed5-102">Details</span><span class="sxs-lookup"><span data-stu-id="1fed5-102">Details</span></span>

<span data-ttu-id="1fed5-103">Ab .NET Framework 4.6 und 4.6.1 tritt bei dem Versuch, eine TCP/IP-Verbindung mit einer SQL Server-Datenbank herzustellen, die zu <code>localhost</code> aufgelöst wird, folgender Fehler auf: &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1fed5-103">In the .NET Framework 4.6 and 4.6.1, attempting a TCP/IP connection to a SQL Server database that resolves to <code>localhost</code> fails with the error, &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span></span> <span data-ttu-id="1fed5-104">Der Server wurde nicht gefunden oder es konnte nicht auf ihn zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="1fed5-104">The server was not found or was not accessible.</span></span> <span data-ttu-id="1fed5-105">Stellen Sie sicher, dass der Instanzname richtig und SQL Server so konfiguriert ist, das Remoteverbindungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="1fed5-105">Verify that the instance name is correct and that SQL Server is configured to allow remote connections.</span></span> <span data-ttu-id="1fed5-106">(Anbieter: SQL-Netzwerkschnittstellen, Fehler: 26 – Fehler beim Auffinden des angegebenen Servers/der angegebenen Instanz)&quot;</span><span class="sxs-lookup"><span data-stu-id="1fed5-106">(provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified)&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1fed5-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1fed5-107">Suggestion</span></span>

<span data-ttu-id="1fed5-108">Dieses Problem wurde behoben und das vorherige Verhalten in .NET Framework 4.6.2 wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="1fed5-108">This issue has been addressed and the previous behavior restored in the .NET Framework 4.6.2.</span></span> <span data-ttu-id="1fed5-109">Führen Sie ein Upgrade auf .NET Framework 4.6.2 durch, um eine Verbindung mit einer SQL Server-Datenbank herzustellen, die zu <code>localhost</code> aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1fed5-109">To connect to a SQL Server database that resolves to <code>localhost</code>, upgrade to the .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="1fed5-110">name</span><span class="sxs-lookup"><span data-stu-id="1fed5-110">Name</span></span>    | <span data-ttu-id="1fed5-111">Wert</span><span class="sxs-lookup"><span data-stu-id="1fed5-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1fed5-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="1fed5-112">Scope</span></span>   |<span data-ttu-id="1fed5-113">Gering</span><span class="sxs-lookup"><span data-stu-id="1fed5-113">Minor</span></span>|
|<span data-ttu-id="1fed5-114">Version</span><span class="sxs-lookup"><span data-stu-id="1fed5-114">Version</span></span>|<span data-ttu-id="1fed5-115">4.6</span><span class="sxs-lookup"><span data-stu-id="1fed5-115">4.6</span></span>|
|<span data-ttu-id="1fed5-116">Typ</span><span class="sxs-lookup"><span data-stu-id="1fed5-116">Type</span></span>|<span data-ttu-id="1fed5-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1fed5-117">Runtime</span></span>|
