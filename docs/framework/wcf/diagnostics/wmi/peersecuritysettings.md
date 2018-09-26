---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
ms.openlocfilehash: c74ee82d7aa3a23f0ee6a69185ad45857c31bb0b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47087878"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="ec7ed-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ec7ed-102">PeerSecuritySettings</span></span>
<span data-ttu-id="ec7ed-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ec7ed-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec7ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec7ed-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ec7ed-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ec7ed-105">Methods</span></span>  
 <span data-ttu-id="ec7ed-106">Die PeerSecuritySettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="ec7ed-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ec7ed-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ec7ed-107">Properties</span></span>  
 <span data-ttu-id="ec7ed-108">Die PeerSecuritySettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ec7ed-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="ec7ed-109">Modus</span><span class="sxs-lookup"><span data-stu-id="ec7ed-109">Mode</span></span>  
 <span data-ttu-id="ec7ed-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ec7ed-110">Data type: string</span></span>  
  
 <span data-ttu-id="ec7ed-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ec7ed-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ec7ed-112">Ob Sicherheit auf Nachrichtenebene und auf Transportebene von einem Endpunkt genutzt wird, der mit der Bindung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="ec7ed-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="ec7ed-113">Transport</span><span class="sxs-lookup"><span data-stu-id="ec7ed-113">Transport</span></span>  
 <span data-ttu-id="ec7ed-114">Datentyp: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ec7ed-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="ec7ed-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ec7ed-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ec7ed-116">Transportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ec7ed-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec7ed-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec7ed-117">Requirements</span></span>  
  
|<span data-ttu-id="ec7ed-118">MOF</span><span class="sxs-lookup"><span data-stu-id="ec7ed-118">MOF</span></span>|<span data-ttu-id="ec7ed-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ec7ed-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ec7ed-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="ec7ed-120">Namespace</span></span>|<span data-ttu-id="ec7ed-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ec7ed-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec7ed-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec7ed-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
