---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 7e6a96c217b038e870b4e865315766afa3b3c757
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975345"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="dd411-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="dd411-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="dd411-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="dd411-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd411-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd411-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="dd411-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="dd411-105">Methods</span></span>  
 <span data-ttu-id="dd411-106">Die MustUnderstandBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="dd411-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dd411-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dd411-107">Properties</span></span>  
 <span data-ttu-id="dd411-108">Die MustUnderstandBehavior-Klasse hat die folgende Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="dd411-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="dd411-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="dd411-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="dd411-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="dd411-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="dd411-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dd411-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd411-112">Wenn der Wert `true` festgelegt wurde, verursachen alle SOAP-Header mit dem `MustUnderstand`-Attribut, die nicht behandelt werden, die Ausgabe einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="dd411-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd411-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd411-113">Requirements</span></span>  
  
|<span data-ttu-id="dd411-114">MOF</span><span class="sxs-lookup"><span data-stu-id="dd411-114">MOF</span></span>|<span data-ttu-id="dd411-115">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dd411-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dd411-116">Namespace</span><span class="sxs-lookup"><span data-stu-id="dd411-116">Namespace</span></span>|<span data-ttu-id="dd411-117">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dd411-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd411-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd411-118">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
