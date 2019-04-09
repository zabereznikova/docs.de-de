---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8c2d4bfc08a503a8d6eb0e8abf6f1e798b90bc83
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095333"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="7d362-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="7d362-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="7d362-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="7d362-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d362-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d362-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7d362-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7d362-105">Methods</span></span>  
 <span data-ttu-id="7d362-106">Die NamedPipeConnectionPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="7d362-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7d362-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d362-107">Properties</span></span>  
 <span data-ttu-id="7d362-108">Die NamedPipeConnectionPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="7d362-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="7d362-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="7d362-109">GroupName</span></span>  
 <span data-ttu-id="7d362-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7d362-110">Data type: string</span></span>  
  
 <span data-ttu-id="7d362-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7d362-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d362-112">Der Gruppenname des vom Bindungselement verwendeten Verbindungspools.</span><span class="sxs-lookup"><span data-stu-id="7d362-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="7d362-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="7d362-113">IdleTimeout</span></span>  
 <span data-ttu-id="7d362-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="7d362-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="7d362-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7d362-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d362-116">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="7d362-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="7d362-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="7d362-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="7d362-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="7d362-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="7d362-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7d362-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d362-120">Die maximale Anzahl von ausgehenden Verbindungen pro Endpunkt auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="7d362-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d362-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d362-121">Requirements</span></span>  
  
|<span data-ttu-id="7d362-122">MOF</span><span class="sxs-lookup"><span data-stu-id="7d362-122">MOF</span></span>|<span data-ttu-id="7d362-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7d362-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7d362-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="7d362-124">Namespace</span></span>|<span data-ttu-id="7d362-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7d362-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d362-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d362-126">See also</span></span>

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
