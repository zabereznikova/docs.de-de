---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 3dddfa878e3cb5bd89fb76009d0dba530debb297
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725076"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="3d0ac-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="3d0ac-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="3d0ac-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="3d0ac-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d0ac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d0ac-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3d0ac-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3d0ac-105">Methods</span></span>  
 <span data-ttu-id="3d0ac-106">Die NamedPipeConnectionPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="3d0ac-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3d0ac-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3d0ac-107">Properties</span></span>  
 <span data-ttu-id="3d0ac-108">Die NamedPipeConnectionPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3d0ac-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="3d0ac-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="3d0ac-109">GroupName</span></span>  
 <span data-ttu-id="3d0ac-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="3d0ac-110">Data type: string</span></span>  
  
 <span data-ttu-id="3d0ac-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3d0ac-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3d0ac-112">Der Gruppenname des vom Bindungselement verwendeten Verbindungspools.</span><span class="sxs-lookup"><span data-stu-id="3d0ac-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="3d0ac-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="3d0ac-113">IdleTimeout</span></span>  
 <span data-ttu-id="3d0ac-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="3d0ac-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="3d0ac-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3d0ac-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3d0ac-116">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="3d0ac-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="3d0ac-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="3d0ac-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="3d0ac-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="3d0ac-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="3d0ac-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3d0ac-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3d0ac-120">Die maximale Anzahl von ausgehenden Verbindungen pro Endpunkt auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="3d0ac-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d0ac-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d0ac-121">Requirements</span></span>  
  
|<span data-ttu-id="3d0ac-122">MOF</span><span class="sxs-lookup"><span data-stu-id="3d0ac-122">MOF</span></span>|<span data-ttu-id="3d0ac-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3d0ac-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3d0ac-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="3d0ac-124">Namespace</span></span>|<span data-ttu-id="3d0ac-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3d0ac-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d0ac-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d0ac-126">See also</span></span>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
