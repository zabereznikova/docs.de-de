---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: de00cac851e4c6d0fd6df16f3a01b65bb5f43415
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294676"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="0f7ff-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="0f7ff-102">TcpConnectionPoolSettings</span></span>

<span data-ttu-id="0f7ff-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="0f7ff-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f7ff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f7ff-104">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0f7ff-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="0f7ff-105">Methods</span></span>  

 <span data-ttu-id="0f7ff-106">Von der TcpConnectionPoolSettings-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="0f7ff-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0f7ff-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0f7ff-107">Properties</span></span>  

 <span data-ttu-id="0f7ff-108">Die TcpConnectionPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="0f7ff-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="0f7ff-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="0f7ff-109">GroupName</span></span>  

 <span data-ttu-id="0f7ff-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="0f7ff-110">Data type: string</span></span>  
  
 <span data-ttu-id="0f7ff-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0f7ff-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0f7ff-112">Der Gruppenname des vom Bindungselement verwendeten Verbindungspools.</span><span class="sxs-lookup"><span data-stu-id="0f7ff-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="0f7ff-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="0f7ff-113">IdleTimeout</span></span>  

 <span data-ttu-id="0f7ff-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="0f7ff-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="0f7ff-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0f7ff-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0f7ff-116">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="0f7ff-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="0f7ff-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="0f7ff-117">LeaseTimeout</span></span>  

 <span data-ttu-id="0f7ff-118">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="0f7ff-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="0f7ff-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0f7ff-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0f7ff-120">Die maximale Zeit für die Ausführung eines Leasevorgangs, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="0f7ff-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="0f7ff-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="0f7ff-121">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="0f7ff-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="0f7ff-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="0f7ff-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0f7ff-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0f7ff-124">Die maximale Anzahl von ausgehenden Verbindungen pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="0f7ff-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f7ff-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f7ff-125">Requirements</span></span>  
  
|<span data-ttu-id="0f7ff-126">MOF</span><span class="sxs-lookup"><span data-stu-id="0f7ff-126">MOF</span></span>|<span data-ttu-id="0f7ff-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0f7ff-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0f7ff-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="0f7ff-128">Namespace</span></span>|<span data-ttu-id="0f7ff-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0f7ff-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f7ff-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f7ff-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
