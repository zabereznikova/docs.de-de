---
title: SymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ab341f55947bfcfbc776143e3bbc33e125da89c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="f571f-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f571f-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="f571f-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f571f-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f571f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f571f-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f571f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f571f-105">Methods</span></span>  
 <span data-ttu-id="f571f-106">Die SymmetricSecurityBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="f571f-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f571f-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f571f-107">Properties</span></span>  
 <span data-ttu-id="f571f-108">Die SymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f571f-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="f571f-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="f571f-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="f571f-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f571f-110">Data type: string</span></span>  
  
 <span data-ttu-id="f571f-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f571f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f571f-112">Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.</span><span class="sxs-lookup"><span data-stu-id="f571f-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="f571f-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="f571f-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="f571f-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f571f-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="f571f-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f571f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f571f-116">Gibt an, ob die Bindung eine Signaturbestätigung erfordert.</span><span class="sxs-lookup"><span data-stu-id="f571f-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f571f-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f571f-117">Requirements</span></span>  
  
|<span data-ttu-id="f571f-118">MOF</span><span class="sxs-lookup"><span data-stu-id="f571f-118">MOF</span></span>|<span data-ttu-id="f571f-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f571f-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f571f-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="f571f-120">Namespace</span></span>|<span data-ttu-id="f571f-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f571f-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f571f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f571f-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
