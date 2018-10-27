---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: 618899c80d1b22aaabc3c13fe1079137eaf10a93
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50182501"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="e5779-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="e5779-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="e5779-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="e5779-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5779-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5779-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e5779-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e5779-105">Methods</span></span>  
 <span data-ttu-id="e5779-106">Die SymmetricSecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="e5779-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e5779-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e5779-107">Properties</span></span>  
 <span data-ttu-id="e5779-108">Die SymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e5779-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="e5779-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="e5779-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="e5779-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e5779-110">Data type: string</span></span>  
  
 <span data-ttu-id="e5779-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e5779-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5779-112">Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="e5779-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="e5779-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="e5779-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="e5779-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e5779-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="e5779-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e5779-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5779-116">Gibt an, ob die Bindung eine Signaturbestätigung erfordert.</span><span class="sxs-lookup"><span data-stu-id="e5779-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5779-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5779-117">Requirements</span></span>  
  
|<span data-ttu-id="e5779-118">MOF</span><span class="sxs-lookup"><span data-stu-id="e5779-118">MOF</span></span>|<span data-ttu-id="e5779-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e5779-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e5779-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="e5779-120">Namespace</span></span>|<span data-ttu-id="e5779-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e5779-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5779-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5779-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
