---
title: PeerSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 48a9cc5a7a05b47a5589d1bf9a730184fb7f0543
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="peersecuritysettings"></a><span data-ttu-id="63778-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="63778-102">PeerSecuritySettings</span></span>
<span data-ttu-id="63778-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="63778-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63778-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63778-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="63778-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="63778-105">Methods</span></span>  
 <span data-ttu-id="63778-106">Die PeerSecuritySettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="63778-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="63778-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="63778-107">Properties</span></span>  
 <span data-ttu-id="63778-108">Die PeerSecuritySettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="63778-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="63778-109">Modus</span><span class="sxs-lookup"><span data-stu-id="63778-109">Mode</span></span>  
 <span data-ttu-id="63778-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="63778-110">Data type: string</span></span>  
  
 <span data-ttu-id="63778-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="63778-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63778-112">Ob Sicherheit auf Nachrichtenebene und auf Transportebene von einem Endpunkt genutzt wird, der mit der Bindung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="63778-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="63778-113">Transport</span><span class="sxs-lookup"><span data-stu-id="63778-113">Transport</span></span>  
 <span data-ttu-id="63778-114">Datentyp: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="63778-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="63778-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="63778-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63778-116">Transportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="63778-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63778-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63778-117">Requirements</span></span>  
  
|<span data-ttu-id="63778-118">MOF</span><span class="sxs-lookup"><span data-stu-id="63778-118">MOF</span></span>|<span data-ttu-id="63778-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="63778-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="63778-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="63778-120">Namespace</span></span>|<span data-ttu-id="63778-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="63778-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63778-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63778-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
