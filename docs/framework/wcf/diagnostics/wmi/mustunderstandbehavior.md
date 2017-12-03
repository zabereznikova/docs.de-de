---
title: MustUnderstandBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 40075acb2a098c98b4cd0ab35f213981c09f8486
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="6a97b-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="6a97b-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="6a97b-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="6a97b-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a97b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a97b-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6a97b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6a97b-105">Methods</span></span>  
 <span data-ttu-id="6a97b-106">Die MustUnderstandBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="6a97b-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6a97b-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6a97b-107">Properties</span></span>  
 <span data-ttu-id="6a97b-108">Die MustUnderstandBehavior-Klasse hat die folgende Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="6a97b-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="6a97b-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="6a97b-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="6a97b-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="6a97b-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="6a97b-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6a97b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6a97b-112">Wenn der Wert `true` festgelegt wurde, verursachen alle SOAP-Header mit dem `MustUnderstand`-Attribut, die nicht behandelt werden, die Ausgabe einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="6a97b-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a97b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a97b-113">Requirements</span></span>  
  
|<span data-ttu-id="6a97b-114">MOF</span><span class="sxs-lookup"><span data-stu-id="6a97b-114">MOF</span></span>|<span data-ttu-id="6a97b-115">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6a97b-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6a97b-116">Namespace</span><span class="sxs-lookup"><span data-stu-id="6a97b-116">Namespace</span></span>|<span data-ttu-id="6a97b-117">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6a97b-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a97b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a97b-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
