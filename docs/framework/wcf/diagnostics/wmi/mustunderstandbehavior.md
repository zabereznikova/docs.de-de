---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 14150a992130e9ed4734c950d4ed92f1bbd3206c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485556"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="84e6f-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="84e6f-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="84e6f-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="84e6f-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e6f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84e6f-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="84e6f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="84e6f-105">Methods</span></span>  
 <span data-ttu-id="84e6f-106">Die MustUnderstandBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="84e6f-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="84e6f-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="84e6f-107">Properties</span></span>  
 <span data-ttu-id="84e6f-108">Die MustUnderstandBehavior-Klasse hat die folgende Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="84e6f-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="84e6f-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="84e6f-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="84e6f-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="84e6f-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="84e6f-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="84e6f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="84e6f-112">Wenn der Wert `true` festgelegt wurde, verursachen alle SOAP-Header mit dem `MustUnderstand`-Attribut, die nicht behandelt werden, die Ausgabe einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="84e6f-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84e6f-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84e6f-113">Requirements</span></span>  
  
|<span data-ttu-id="84e6f-114">MOF</span><span class="sxs-lookup"><span data-stu-id="84e6f-114">MOF</span></span>|<span data-ttu-id="84e6f-115">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="84e6f-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="84e6f-116">Namespace</span><span class="sxs-lookup"><span data-stu-id="84e6f-116">Namespace</span></span>|<span data-ttu-id="84e6f-117">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="84e6f-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84e6f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84e6f-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
