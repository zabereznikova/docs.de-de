---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 58b372f26fee7dc180d75731fd4855db569c87c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484519"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="ee499-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ee499-102">PeerSecuritySettings</span></span>
<span data-ttu-id="ee499-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ee499-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee499-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee499-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ee499-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ee499-105">Methods</span></span>  
 <span data-ttu-id="ee499-106">Die PeerSecuritySettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="ee499-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ee499-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ee499-107">Properties</span></span>  
 <span data-ttu-id="ee499-108">Die PeerSecuritySettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ee499-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="ee499-109">Modus</span><span class="sxs-lookup"><span data-stu-id="ee499-109">Mode</span></span>  
 <span data-ttu-id="ee499-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ee499-110">Data type: string</span></span>  
  
 <span data-ttu-id="ee499-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee499-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee499-112">Ob Sicherheit auf Nachrichtenebene und auf Transportebene von einem Endpunkt genutzt wird, der mit der Bindung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="ee499-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="ee499-113">Transport</span><span class="sxs-lookup"><span data-stu-id="ee499-113">Transport</span></span>  
 <span data-ttu-id="ee499-114">Datentyp: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ee499-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="ee499-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee499-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee499-116">Transportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ee499-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee499-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee499-117">Requirements</span></span>  
  
|<span data-ttu-id="ee499-118">MOF</span><span class="sxs-lookup"><span data-stu-id="ee499-118">MOF</span></span>|<span data-ttu-id="ee499-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ee499-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ee499-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="ee499-120">Namespace</span></span>|<span data-ttu-id="ee499-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ee499-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee499-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee499-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
