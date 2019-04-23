---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 0f86fc1b410753b5ec100f0a7d43de9badd1401b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59978067"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="88c1b-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="88c1b-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="88c1b-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="88c1b-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88c1b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="88c1b-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="88c1b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="88c1b-105">Methods</span></span>  
 <span data-ttu-id="88c1b-106">Die AsymmetricSecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="88c1b-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="88c1b-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="88c1b-107">Properties</span></span>  
 <span data-ttu-id="88c1b-108">Die AsymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="88c1b-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="88c1b-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="88c1b-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="88c1b-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="88c1b-110">Data type: string</span></span>  
  
 <span data-ttu-id="88c1b-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="88c1b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88c1b-112">Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="88c1b-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="88c1b-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="88c1b-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="88c1b-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="88c1b-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="88c1b-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="88c1b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88c1b-116">Gibt an, ob die Bindung eine Signaturbestätigung erfordert.</span><span class="sxs-lookup"><span data-stu-id="88c1b-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88c1b-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="88c1b-117">Requirements</span></span>  
  
|<span data-ttu-id="88c1b-118">MOF</span><span class="sxs-lookup"><span data-stu-id="88c1b-118">MOF</span></span>|<span data-ttu-id="88c1b-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="88c1b-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="88c1b-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="88c1b-120">Namespace</span></span>|<span data-ttu-id="88c1b-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="88c1b-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88c1b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88c1b-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
