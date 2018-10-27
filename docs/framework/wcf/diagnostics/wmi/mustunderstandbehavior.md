---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 0f3efc446104a1afff507f6e7d2cd8c01c4ed417
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452598"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="67dda-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="67dda-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="67dda-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="67dda-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67dda-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67dda-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="67dda-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="67dda-105">Methods</span></span>  
 <span data-ttu-id="67dda-106">Die MustUnderstandBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="67dda-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="67dda-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="67dda-107">Properties</span></span>  
 <span data-ttu-id="67dda-108">Die MustUnderstandBehavior-Klasse hat die folgende Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="67dda-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="67dda-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="67dda-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="67dda-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="67dda-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="67dda-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="67dda-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="67dda-112">Wenn der Wert `true` festgelegt wurde, verursachen alle SOAP-Header mit dem `MustUnderstand`-Attribut, die nicht behandelt werden, die Ausgabe einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="67dda-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67dda-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67dda-113">Requirements</span></span>  
  
|<span data-ttu-id="67dda-114">MOF</span><span class="sxs-lookup"><span data-stu-id="67dda-114">MOF</span></span>|<span data-ttu-id="67dda-115">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="67dda-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="67dda-116">Namespace</span><span class="sxs-lookup"><span data-stu-id="67dda-116">Namespace</span></span>|<span data-ttu-id="67dda-117">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="67dda-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67dda-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67dda-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
