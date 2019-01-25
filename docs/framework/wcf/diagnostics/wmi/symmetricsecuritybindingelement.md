---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: 7b979a6872da15c4130e580a3f7327802f42db18
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701390"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="59b66-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="59b66-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="59b66-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="59b66-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b66-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59b66-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="59b66-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="59b66-105">Methods</span></span>  
 <span data-ttu-id="59b66-106">Die SymmetricSecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="59b66-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="59b66-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="59b66-107">Properties</span></span>  
 <span data-ttu-id="59b66-108">Die SymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="59b66-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="59b66-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="59b66-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="59b66-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="59b66-110">Data type: string</span></span>  
  
 <span data-ttu-id="59b66-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="59b66-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59b66-112">Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="59b66-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="59b66-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="59b66-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="59b66-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="59b66-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="59b66-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="59b66-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59b66-116">Gibt an, ob die Bindung eine Signaturbestätigung erfordert.</span><span class="sxs-lookup"><span data-stu-id="59b66-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b66-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="59b66-117">Requirements</span></span>  
  
|<span data-ttu-id="59b66-118">MOF</span><span class="sxs-lookup"><span data-stu-id="59b66-118">MOF</span></span>|<span data-ttu-id="59b66-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="59b66-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="59b66-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="59b66-120">Namespace</span></span>|<span data-ttu-id="59b66-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="59b66-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59b66-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59b66-122">See also</span></span>
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
