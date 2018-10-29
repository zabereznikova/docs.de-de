---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 1a5284915de739e95325234318842a4d1ab607be
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50196968"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="0aa1c-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="0aa1c-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="0aa1c-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="0aa1c-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aa1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0aa1c-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0aa1c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="0aa1c-105">Methods</span></span>  
 <span data-ttu-id="0aa1c-106">Die ServiceTimeoutsBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="0aa1c-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0aa1c-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0aa1c-107">Properties</span></span>  
 <span data-ttu-id="0aa1c-108">Die ServiceTimeoutsBehavior-Klasse verfügt über die folgende Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="0aa1c-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="0aa1c-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="0aa1c-109">TransactionTimeout</span></span>  
 <span data-ttu-id="0aa1c-110">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="0aa1c-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="0aa1c-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0aa1c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0aa1c-112">Der Zeitraum, in dem eine Transaktion abgeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="0aa1c-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aa1c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0aa1c-113">Requirements</span></span>  
  
|<span data-ttu-id="0aa1c-114">MOF</span><span class="sxs-lookup"><span data-stu-id="0aa1c-114">MOF</span></span>|<span data-ttu-id="0aa1c-115">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0aa1c-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0aa1c-116">Namespace</span><span class="sxs-lookup"><span data-stu-id="0aa1c-116">Namespace</span></span>|<span data-ttu-id="0aa1c-117">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0aa1c-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0aa1c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0aa1c-118">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
