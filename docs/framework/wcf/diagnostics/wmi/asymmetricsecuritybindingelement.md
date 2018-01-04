---
title: AsymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 82e5365a440d103727f354e682d0ebecb5f46a46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="d37c9-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d37c9-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="d37c9-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d37c9-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d37c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d37c9-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d37c9-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d37c9-105">Methods</span></span>  
 <span data-ttu-id="d37c9-106">Die AsymmetricSecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="d37c9-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d37c9-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d37c9-107">Properties</span></span>  
 <span data-ttu-id="d37c9-108">Die AsymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d37c9-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="d37c9-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="d37c9-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="d37c9-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d37c9-110">Data type: string</span></span>  
  
 <span data-ttu-id="d37c9-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d37c9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d37c9-112">Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="d37c9-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="d37c9-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="d37c9-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="d37c9-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d37c9-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="d37c9-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d37c9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d37c9-116">Gibt an, ob die Bindung eine Signaturbestätigung erfordert.</span><span class="sxs-lookup"><span data-stu-id="d37c9-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d37c9-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d37c9-117">Requirements</span></span>  
  
|<span data-ttu-id="d37c9-118">MOF</span><span class="sxs-lookup"><span data-stu-id="d37c9-118">MOF</span></span>|<span data-ttu-id="d37c9-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d37c9-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d37c9-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="d37c9-120">Namespace</span></span>|<span data-ttu-id="d37c9-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d37c9-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d37c9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d37c9-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
