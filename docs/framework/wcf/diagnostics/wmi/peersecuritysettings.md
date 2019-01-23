---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 761ed0e30c6acca8c910c5dc97dfbae46c1f89bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564837"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="62886-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="62886-102">PeerSecuritySettings</span></span>
<span data-ttu-id="62886-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="62886-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62886-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62886-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="62886-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="62886-105">Methods</span></span>  
 <span data-ttu-id="62886-106">Die PeerSecuritySettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="62886-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="62886-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="62886-107">Properties</span></span>  
 <span data-ttu-id="62886-108">Die PeerSecuritySettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="62886-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="62886-109">Modus</span><span class="sxs-lookup"><span data-stu-id="62886-109">Mode</span></span>  
 <span data-ttu-id="62886-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="62886-110">Data type: string</span></span>  
  
 <span data-ttu-id="62886-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="62886-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62886-112">Ob Sicherheit auf Nachrichtenebene und auf Transportebene von einem Endpunkt genutzt wird, der mit der Bindung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="62886-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="62886-113">Transport</span><span class="sxs-lookup"><span data-stu-id="62886-113">Transport</span></span>  
 <span data-ttu-id="62886-114">Datentyp: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="62886-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="62886-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="62886-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62886-116">Transportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="62886-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62886-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62886-117">Requirements</span></span>  
  
|<span data-ttu-id="62886-118">MOF</span><span class="sxs-lookup"><span data-stu-id="62886-118">MOF</span></span>|<span data-ttu-id="62886-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="62886-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="62886-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="62886-120">Namespace</span></span>|<span data-ttu-id="62886-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="62886-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62886-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62886-122">See also</span></span>
- <xref:System.ServiceModel.PeerSecuritySettings>
