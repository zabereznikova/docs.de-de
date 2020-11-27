---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 9cac7192d5c34de55fe0bd6a4921a41387e985f8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250436"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="9b6da-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="9b6da-102">MustUnderstandBehavior</span></span>

<span data-ttu-id="9b6da-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="9b6da-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b6da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b6da-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9b6da-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9b6da-105">Methods</span></span>  

 <span data-ttu-id="9b6da-106">Die MustUnderstandBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="9b6da-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9b6da-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9b6da-107">Properties</span></span>  

 <span data-ttu-id="9b6da-108">Die MustUnderstandBehavior-Klasse hat die folgende Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="9b6da-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="9b6da-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="9b6da-109">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="9b6da-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="9b6da-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="9b6da-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9b6da-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9b6da-112">Wenn der Wert `true` festgelegt wurde, verursachen alle SOAP-Header mit dem `MustUnderstand`-Attribut, die nicht behandelt werden, die Ausgabe einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="9b6da-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b6da-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b6da-113">Requirements</span></span>  
  
|<span data-ttu-id="9b6da-114">MOF</span><span class="sxs-lookup"><span data-stu-id="9b6da-114">MOF</span></span>|<span data-ttu-id="9b6da-115">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9b6da-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9b6da-116">Namespace</span><span class="sxs-lookup"><span data-stu-id="9b6da-116">Namespace</span></span>|<span data-ttu-id="9b6da-117">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9b6da-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b6da-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b6da-118">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
