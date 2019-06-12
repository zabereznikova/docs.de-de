---
title: 'Entschärfung: Poolsperrfrist'
ms.date: 03/30/2017
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01bd548bbafda34202705dda3dda148aae941e2b
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251104"
---
# <a name="mitigation-pool-blocking-period"></a><span data-ttu-id="bca99-102">Entschärfung: Poolsperrfrist</span><span class="sxs-lookup"><span data-stu-id="bca99-102">Mitigation: Pool Blocking Period</span></span>
<span data-ttu-id="bca99-103">Die Sperrfrist für den Verbindungspool wurde für Verbindungen mit Azure SQL-Datenbanken entfernt.</span><span class="sxs-lookup"><span data-stu-id="bca99-103">The connection pool blocking period has been removed for connections to Azure SQL databases.</span></span>  
  
## <a name="additional-description"></a><span data-ttu-id="bca99-104">Zusätzliche Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bca99-104">Additional description</span></span>  
 <span data-ttu-id="bca99-105">Wenn in .NET Framework 4.6.1 und früheren Versionen eine App einen vorübergehender Verbindungsfehler beim Herstellen der Verbindung mit der Datenbank erkennt, kann der Verbindungsversuch nicht schnell wiederholt werden, da der Fehler vom Verbindungspool zwischengespeichert und für einen Zeitraum von fünf bis 60 Sekunden erneut ausgelöst wird. Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="bca99-105">In the .NET Framework 4.6.1 and earlier versions, when an app encounters a transient connection failure when connecting to a database, the connection attempt cannot be retried quickly, because the connection pool caches the error and re-throws it for 5 seconds to 1 min. For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span> <span data-ttu-id="bca99-106">Dieses Verhalten ist für Verbindungen mit Azure SQL-Datenbanken problematisch, die häufig aufgrund vorübergehender Fehler fehlschlagen, die in der Regel innerhalb weniger Sekunden behoben sind.</span><span class="sxs-lookup"><span data-stu-id="bca99-106">This behavior is problematic for connections to Azure SQL databases, which often fail with transient errors that are typically recovered from within a few seconds.</span></span> <span data-ttu-id="bca99-107">Das Sperrfeature des Verbindungspools bedeutet, dass die App für einen längeren Zeitraum keine Verbindung mit der Datenbank herstellen kann, auch wenn die Datenbank verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bca99-107">The connection pool blocking feature means that the app cannot connect to the database for an extensive period, even though the database is available.</span></span> <span data-ttu-id="bca99-108">Dieses Verhalten ist besonders problematisch für Web-Apps, die eine Verbindung mit Azure SQL-Datenbanken herstellen und die innerhalb von wenigen Sekunden gerendert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bca99-108">This behavior is particularly problematic for web apps that connect to Azure SQL databases and that need to render within a few seconds.</span></span>  
  
 <span data-ttu-id="bca99-109">Ab .NET Framework 4.6.2 werden Fehler bei Anforderungen zum Öffnen von Verbindungen mit bekannten Azure SQL-Datenbanken (\*.database.Windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de) nicht mehr zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="bca99-109">Starting with the .NET Framework 4.6.2, for connection open requests to known Azure SQL databases (\*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), connection open errors are not cached.</span></span> <span data-ttu-id="bca99-110">Für alle anderen Verbindungsversuche wird die Sperrfrist für den Verbindungspool weiterhin erzwungen.</span><span class="sxs-lookup"><span data-stu-id="bca99-110">For all other connection attempts, the connection pool blocking period continues to be enforced.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="bca99-111">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="bca99-111">Impact</span></span>  
 <span data-ttu-id="bca99-112">Diese Änderung ermöglicht die sofortige Wiederholung eines Versuchs zum Öffnen einer Verbindung mit Azure SQL-Datenbanken. Dadurch wird die Leistung von cloudfähigen Apps verbessert.</span><span class="sxs-lookup"><span data-stu-id="bca99-112">This change allows the connection open attempt to be retried immediately for Azure SQL databases, thereby improving the performance of cloud-enabled apps.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="bca99-113">Minderung</span><span class="sxs-lookup"><span data-stu-id="bca99-113">Mitigation</span></span>  
 <span data-ttu-id="bca99-114">Für Apps, die von dieser Änderung negativ betroffen sind, kann die Sperrfrist für den Verbindungspool konfiguriert werden, indem die neue <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A?displayProperty=nameWithType>-Eigenschaft festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="bca99-114">For apps that are adversely affected by this change, the connection pool blocking period can be configured by setting the new <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="bca99-115">Der Wert der Eigenschaft ist ein Mitglied der <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType>-Enumeration, die einen von drei Werten annehmen kann:</span><span class="sxs-lookup"><span data-stu-id="bca99-115">The value of the property is a member of the <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> enumeration that can take either of three values:</span></span>  
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.Auto?displayProperty=nameWithType>
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock?displayProperty=nameWithType>
  
 <span data-ttu-id="bca99-116">Das vorherige Verhalten kann wiederhergestellt werden, indem Sie die <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A>-Eigenschaft auf <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType> festlegen.</span><span class="sxs-lookup"><span data-stu-id="bca99-116">The previous behavior can be restored by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> property to <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca99-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bca99-117">See also</span></span>

- [<span data-ttu-id="bca99-118">Änderungen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="bca99-118">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
