---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 00485ff80a0064e700d99203de3aa581d3761f30
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255727"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="b3a05-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b3a05-102">AsymmetricSecurityBindingElement</span></span>

<span data-ttu-id="b3a05-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b3a05-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3a05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3a05-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b3a05-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b3a05-105">Methods</span></span>  

 <span data-ttu-id="b3a05-106">Die AsymmetricSecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="b3a05-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b3a05-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b3a05-107">Properties</span></span>  

 <span data-ttu-id="b3a05-108">Die AsymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="b3a05-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="b3a05-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="b3a05-109">MessageProtectionOrder</span></span>  

 <span data-ttu-id="b3a05-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="b3a05-110">Data type: string</span></span>  
  
 <span data-ttu-id="b3a05-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3a05-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3a05-112">Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="b3a05-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="b3a05-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="b3a05-113">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="b3a05-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="b3a05-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b3a05-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3a05-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3a05-116">Gibt an, ob die Bindung eine Signaturbestätigung erfordert.</span><span class="sxs-lookup"><span data-stu-id="b3a05-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3a05-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3a05-117">Requirements</span></span>  
  
|<span data-ttu-id="b3a05-118">MOF</span><span class="sxs-lookup"><span data-stu-id="b3a05-118">MOF</span></span>|<span data-ttu-id="b3a05-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b3a05-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b3a05-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="b3a05-120">Namespace</span></span>|<span data-ttu-id="b3a05-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b3a05-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3a05-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3a05-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
