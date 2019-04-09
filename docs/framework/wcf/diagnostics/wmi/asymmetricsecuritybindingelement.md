---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 0f86fc1b410753b5ec100f0a7d43de9badd1401b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196046"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="1743d-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1743d-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="1743d-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1743d-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1743d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1743d-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1743d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1743d-105">Methods</span></span>  
 <span data-ttu-id="1743d-106">Die AsymmetricSecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="1743d-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1743d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1743d-107">Properties</span></span>  
 <span data-ttu-id="1743d-108">Die AsymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1743d-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="1743d-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="1743d-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="1743d-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="1743d-110">Data type: string</span></span>  
  
 <span data-ttu-id="1743d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1743d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1743d-112">Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="1743d-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="1743d-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="1743d-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="1743d-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="1743d-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="1743d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1743d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1743d-116">Gibt an, ob die Bindung eine Signaturbestätigung erfordert.</span><span class="sxs-lookup"><span data-stu-id="1743d-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1743d-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1743d-117">Requirements</span></span>  
  
|<span data-ttu-id="1743d-118">MOF</span><span class="sxs-lookup"><span data-stu-id="1743d-118">MOF</span></span>|<span data-ttu-id="1743d-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1743d-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1743d-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="1743d-120">Namespace</span></span>|<span data-ttu-id="1743d-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1743d-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1743d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1743d-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
