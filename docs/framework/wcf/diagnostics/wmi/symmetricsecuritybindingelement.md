---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: c618b5b41790b04a84b4c50fe47baa2c0cb05ab2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274100"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="3fab5-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3fab5-102">SymmetricSecurityBindingElement</span></span>

<span data-ttu-id="3fab5-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3fab5-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fab5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fab5-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3fab5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3fab5-105">Methods</span></span>  

 <span data-ttu-id="3fab5-106">Die SymmetricSecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="3fab5-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3fab5-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3fab5-107">Properties</span></span>  

 <span data-ttu-id="3fab5-108">Die SymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3fab5-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="3fab5-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="3fab5-109">MessageProtectionOrder</span></span>  

 <span data-ttu-id="3fab5-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="3fab5-110">Data type: string</span></span>  
  
 <span data-ttu-id="3fab5-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3fab5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fab5-112">Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="3fab5-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="3fab5-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="3fab5-113">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="3fab5-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="3fab5-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="3fab5-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3fab5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fab5-116">Gibt an, ob die Bindung eine Signaturbestätigung erfordert.</span><span class="sxs-lookup"><span data-stu-id="3fab5-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fab5-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3fab5-117">Requirements</span></span>  
  
|<span data-ttu-id="3fab5-118">MOF</span><span class="sxs-lookup"><span data-stu-id="3fab5-118">MOF</span></span>|<span data-ttu-id="3fab5-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3fab5-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3fab5-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="3fab5-120">Namespace</span></span>|<span data-ttu-id="3fab5-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3fab5-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3fab5-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fab5-122">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
