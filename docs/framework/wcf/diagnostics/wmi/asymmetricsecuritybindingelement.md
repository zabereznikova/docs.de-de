---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
author: BrucePerlerMS
ms.openlocfilehash: 63af1c9a607cb9f81e2c0abf795ee2b3432cbf9c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397357"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="16aee-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="16aee-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="16aee-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="16aee-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16aee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16aee-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="16aee-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="16aee-105">Methods</span></span>  
 <span data-ttu-id="16aee-106">Die AsymmetricSecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="16aee-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="16aee-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="16aee-107">Properties</span></span>  
 <span data-ttu-id="16aee-108">Die AsymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="16aee-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="16aee-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="16aee-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="16aee-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="16aee-110">Data type: string</span></span>  
  
 <span data-ttu-id="16aee-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="16aee-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="16aee-112">Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="16aee-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="16aee-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="16aee-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="16aee-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="16aee-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="16aee-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="16aee-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="16aee-116">Gibt an, ob die Bindung eine Signaturbestätigung erfordert.</span><span class="sxs-lookup"><span data-stu-id="16aee-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16aee-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="16aee-117">Requirements</span></span>  
  
|<span data-ttu-id="16aee-118">MOF</span><span class="sxs-lookup"><span data-stu-id="16aee-118">MOF</span></span>|<span data-ttu-id="16aee-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="16aee-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="16aee-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="16aee-120">Namespace</span></span>|<span data-ttu-id="16aee-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="16aee-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16aee-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16aee-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
