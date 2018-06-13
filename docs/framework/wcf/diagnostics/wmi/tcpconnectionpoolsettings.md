---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 4a30ad3ddfef5d39942345b0e0d5274eeff8e596
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485920"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="2aa9b-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="2aa9b-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="2aa9b-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="2aa9b-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aa9b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2aa9b-104">Syntax</span></span>  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2aa9b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2aa9b-105">Methods</span></span>  
 <span data-ttu-id="2aa9b-106">Von der TcpConnectionPoolSettings-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2aa9b-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2aa9b-107">Properties</span></span>  
 <span data-ttu-id="2aa9b-108">Die TcpConnectionPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="2aa9b-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="2aa9b-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="2aa9b-109">GroupName</span></span>  
 <span data-ttu-id="2aa9b-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="2aa9b-110">Data type: string</span></span>  
  
 <span data-ttu-id="2aa9b-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2aa9b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa9b-112">Der Gruppenname des vom Bindungselement verwendeten Verbindungspools.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="2aa9b-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="2aa9b-113">IdleTimeout</span></span>  
 <span data-ttu-id="2aa9b-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="2aa9b-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="2aa9b-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2aa9b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa9b-116">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="2aa9b-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="2aa9b-117">LeaseTimeout</span></span>  
 <span data-ttu-id="2aa9b-118">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="2aa9b-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="2aa9b-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2aa9b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa9b-120">Die maximale Zeit für die Ausführung eines Leasevorgangs, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="2aa9b-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="2aa9b-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="2aa9b-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="2aa9b-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="2aa9b-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2aa9b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa9b-124">Die maximale Anzahl von ausgehenden Verbindungen pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aa9b-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2aa9b-125">Requirements</span></span>  
  
|<span data-ttu-id="2aa9b-126">MOF</span><span class="sxs-lookup"><span data-stu-id="2aa9b-126">MOF</span></span>|<span data-ttu-id="2aa9b-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2aa9b-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="2aa9b-128">Namespace</span></span>|<span data-ttu-id="2aa9b-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2aa9b-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2aa9b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2aa9b-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
