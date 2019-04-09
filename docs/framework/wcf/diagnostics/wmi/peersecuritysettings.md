---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 1c33e1ce710fea3b1698a6dab47a199e40388f5a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217886"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="d93c6-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d93c6-102">PeerSecuritySettings</span></span>
<span data-ttu-id="d93c6-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d93c6-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d93c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d93c6-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d93c6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d93c6-105">Methods</span></span>  
 <span data-ttu-id="d93c6-106">Die PeerSecuritySettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="d93c6-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d93c6-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d93c6-107">Properties</span></span>  
 <span data-ttu-id="d93c6-108">Die PeerSecuritySettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d93c6-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="d93c6-109">Modus</span><span class="sxs-lookup"><span data-stu-id="d93c6-109">Mode</span></span>  
 <span data-ttu-id="d93c6-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d93c6-110">Data type: string</span></span>  
  
 <span data-ttu-id="d93c6-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d93c6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d93c6-112">Ob Sicherheit auf Nachrichtenebene und auf Transportebene von einem Endpunkt genutzt wird, der mit der Bindung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="d93c6-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="d93c6-113">Transport</span><span class="sxs-lookup"><span data-stu-id="d93c6-113">Transport</span></span>  
 <span data-ttu-id="d93c6-114">Datentyp: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d93c6-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="d93c6-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d93c6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d93c6-116">Transportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="d93c6-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d93c6-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d93c6-117">Requirements</span></span>  
  
|<span data-ttu-id="d93c6-118">MOF</span><span class="sxs-lookup"><span data-stu-id="d93c6-118">MOF</span></span>|<span data-ttu-id="d93c6-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d93c6-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d93c6-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="d93c6-120">Namespace</span></span>|<span data-ttu-id="d93c6-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d93c6-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d93c6-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d93c6-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
