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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dca98f1d8d5f868285ecf11c01122f795ee6cfd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="f662a-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="f662a-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="f662a-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="f662a-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f662a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f662a-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f662a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f662a-105">Methods</span></span>  
 <span data-ttu-id="f662a-106">Die MustUnderstandBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="f662a-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f662a-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f662a-107">Properties</span></span>  
 <span data-ttu-id="f662a-108">Die MustUnderstandBehavior-Klasse hat die folgende Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="f662a-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="f662a-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="f662a-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="f662a-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f662a-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="f662a-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f662a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f662a-112">Wenn der Wert `true` festgelegt wurde, verursachen alle SOAP-Header mit dem `MustUnderstand`-Attribut, die nicht behandelt werden, die Ausgabe einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="f662a-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f662a-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f662a-113">Requirements</span></span>  
  
|<span data-ttu-id="f662a-114">MOF</span><span class="sxs-lookup"><span data-stu-id="f662a-114">MOF</span></span>|<span data-ttu-id="f662a-115">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f662a-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f662a-116">Namespace</span><span class="sxs-lookup"><span data-stu-id="f662a-116">Namespace</span></span>|<span data-ttu-id="f662a-117">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f662a-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f662a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f662a-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
