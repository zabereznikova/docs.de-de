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
ms.openlocfilehash: 02cd483f2f7ec5e599b286b672d051a0e8d57940
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="peersecuritysettings"></a><span data-ttu-id="47772-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="47772-102">PeerSecuritySettings</span></span>
<span data-ttu-id="47772-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="47772-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47772-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47772-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="47772-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="47772-105">Methods</span></span>  
 <span data-ttu-id="47772-106">Die PeerSecuritySettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="47772-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="47772-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="47772-107">Properties</span></span>  
 <span data-ttu-id="47772-108">Die PeerSecuritySettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="47772-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="47772-109">Modus</span><span class="sxs-lookup"><span data-stu-id="47772-109">Mode</span></span>  
 <span data-ttu-id="47772-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="47772-110">Data type: string</span></span>  
  
 <span data-ttu-id="47772-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47772-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47772-112">Ob Sicherheit auf Nachrichtenebene und auf Transportebene von einem Endpunkt genutzt wird, der mit der Bindung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="47772-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="47772-113">Transport</span><span class="sxs-lookup"><span data-stu-id="47772-113">Transport</span></span>  
 <span data-ttu-id="47772-114">Datentyp: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="47772-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="47772-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="47772-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47772-116">Transportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="47772-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47772-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47772-117">Requirements</span></span>  
  
|<span data-ttu-id="47772-118">MOF</span><span class="sxs-lookup"><span data-stu-id="47772-118">MOF</span></span>|<span data-ttu-id="47772-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="47772-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="47772-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="47772-120">Namespace</span></span>|<span data-ttu-id="47772-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="47772-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47772-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47772-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
