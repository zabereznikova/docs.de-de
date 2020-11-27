---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 867219130fc853f3ba2c1c2f807b1651f6480f13
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273970"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="aa79a-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="aa79a-102">ServiceTimeoutsBehavior</span></span>

<span data-ttu-id="aa79a-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="aa79a-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa79a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa79a-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="aa79a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="aa79a-105">Methods</span></span>  

 <span data-ttu-id="aa79a-106">Die ServiceTimeoutsBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="aa79a-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="aa79a-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="aa79a-107">Properties</span></span>  

 <span data-ttu-id="aa79a-108">Die ServiceTimeoutsBehavior-Klasse verfügt über die folgende Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="aa79a-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="aa79a-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="aa79a-109">TransactionTimeout</span></span>  

 <span data-ttu-id="aa79a-110">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="aa79a-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="aa79a-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="aa79a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aa79a-112">Der Zeitraum, in dem eine Transaktion abgeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="aa79a-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa79a-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa79a-113">Requirements</span></span>  
  
|<span data-ttu-id="aa79a-114">MOF</span><span class="sxs-lookup"><span data-stu-id="aa79a-114">MOF</span></span>|<span data-ttu-id="aa79a-115">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="aa79a-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="aa79a-116">Namespace</span><span class="sxs-lookup"><span data-stu-id="aa79a-116">Namespace</span></span>|<span data-ttu-id="aa79a-117">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="aa79a-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa79a-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa79a-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
