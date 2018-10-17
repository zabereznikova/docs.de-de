---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
ms.openlocfilehash: e633ae19cd17930fb140a93ffd0910c7ed8efea4
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374424"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="a7e59-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a7e59-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="a7e59-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a7e59-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e59-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7e59-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a7e59-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a7e59-105">Methods</span></span>  
 <span data-ttu-id="a7e59-106">Die SymmetricSecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="a7e59-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a7e59-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a7e59-107">Properties</span></span>  
 <span data-ttu-id="a7e59-108">Die SymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a7e59-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="a7e59-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="a7e59-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="a7e59-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a7e59-110">Data type: string</span></span>  
  
 <span data-ttu-id="a7e59-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a7e59-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a7e59-112">Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="a7e59-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="a7e59-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="a7e59-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="a7e59-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a7e59-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="a7e59-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a7e59-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a7e59-116">Gibt an, ob die Bindung eine Signaturbestätigung erfordert.</span><span class="sxs-lookup"><span data-stu-id="a7e59-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7e59-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7e59-117">Requirements</span></span>  
  
|<span data-ttu-id="a7e59-118">MOF</span><span class="sxs-lookup"><span data-stu-id="a7e59-118">MOF</span></span>|<span data-ttu-id="a7e59-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a7e59-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a7e59-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="a7e59-120">Namespace</span></span>|<span data-ttu-id="a7e59-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a7e59-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7e59-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7e59-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
