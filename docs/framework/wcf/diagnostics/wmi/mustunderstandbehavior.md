---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 0f3efc446104a1afff507f6e7d2cd8c01c4ed417
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371795"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="3d18e-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="3d18e-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="3d18e-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="3d18e-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d18e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d18e-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3d18e-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3d18e-105">Methods</span></span>  
 <span data-ttu-id="3d18e-106">Die MustUnderstandBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="3d18e-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3d18e-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3d18e-107">Properties</span></span>  
 <span data-ttu-id="3d18e-108">Die MustUnderstandBehavior-Klasse hat die folgende Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="3d18e-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="3d18e-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="3d18e-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="3d18e-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="3d18e-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="3d18e-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3d18e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3d18e-112">Wenn der Wert `true` festgelegt wurde, verursachen alle SOAP-Header mit dem `MustUnderstand`-Attribut, die nicht behandelt werden, die Ausgabe einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="3d18e-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d18e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d18e-113">Requirements</span></span>  
  
|<span data-ttu-id="3d18e-114">MOF</span><span class="sxs-lookup"><span data-stu-id="3d18e-114">MOF</span></span>|<span data-ttu-id="3d18e-115">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3d18e-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3d18e-116">Namespace</span><span class="sxs-lookup"><span data-stu-id="3d18e-116">Namespace</span></span>|<span data-ttu-id="3d18e-117">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3d18e-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d18e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d18e-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
