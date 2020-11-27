---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 2de417e4a4f5c6197551c1408da6907e2fa7c635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269001"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="48c22-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="48c22-102">PeerSecuritySettings</span></span>

<span data-ttu-id="48c22-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="48c22-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48c22-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48c22-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="48c22-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="48c22-105">Methods</span></span>  

 <span data-ttu-id="48c22-106">Die PeerSecuritySettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="48c22-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="48c22-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="48c22-107">Properties</span></span>  

 <span data-ttu-id="48c22-108">Die PeerSecuritySettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="48c22-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="48c22-109">Mode</span><span class="sxs-lookup"><span data-stu-id="48c22-109">Mode</span></span>  

 <span data-ttu-id="48c22-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="48c22-110">Data type: string</span></span>  
  
 <span data-ttu-id="48c22-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="48c22-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="48c22-112">Ob Sicherheit auf Nachrichtenebene und auf Transportebene von einem Endpunkt genutzt wird, der mit der Bindung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="48c22-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="48c22-113">Transport</span><span class="sxs-lookup"><span data-stu-id="48c22-113">Transport</span></span>  

 <span data-ttu-id="48c22-114">Datentyp: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="48c22-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="48c22-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="48c22-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="48c22-116">Transportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="48c22-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48c22-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48c22-117">Requirements</span></span>  
  
|<span data-ttu-id="48c22-118">MOF</span><span class="sxs-lookup"><span data-stu-id="48c22-118">MOF</span></span>|<span data-ttu-id="48c22-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="48c22-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="48c22-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="48c22-120">Namespace</span></span>|<span data-ttu-id="48c22-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="48c22-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48c22-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48c22-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
