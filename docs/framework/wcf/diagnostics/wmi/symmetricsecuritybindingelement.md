---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: f6effd533a205d0e8fd1421119e325f06b340dd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956714"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="3afc7-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3afc7-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="3afc7-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3afc7-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3afc7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3afc7-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3afc7-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3afc7-105">Methods</span></span>  
 <span data-ttu-id="3afc7-106">Die SymmetricSecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="3afc7-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3afc7-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3afc7-107">Properties</span></span>  
 <span data-ttu-id="3afc7-108">Die SymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3afc7-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="3afc7-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="3afc7-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="3afc7-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="3afc7-110">Data type: string</span></span>  
  
 <span data-ttu-id="3afc7-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3afc7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-112">Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="3afc7-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="3afc7-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="3afc7-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="3afc7-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="3afc7-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="3afc7-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3afc7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3afc7-116">Gibt an, ob die Bindung eine Signaturbestätigung erfordert.</span><span class="sxs-lookup"><span data-stu-id="3afc7-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3afc7-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3afc7-117">Requirements</span></span>  
  
|<span data-ttu-id="3afc7-118">MOF</span><span class="sxs-lookup"><span data-stu-id="3afc7-118">MOF</span></span>|<span data-ttu-id="3afc7-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3afc7-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3afc7-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="3afc7-120">Namespace</span></span>|<span data-ttu-id="3afc7-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3afc7-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3afc7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3afc7-122">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
