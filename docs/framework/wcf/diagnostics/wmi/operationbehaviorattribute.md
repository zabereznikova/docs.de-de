---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: d0bf59e6064748a045f761777a2f8f3e88f1cb5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504326"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="d1666-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="d1666-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="d1666-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="d1666-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1666-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1666-104">Syntax</span></span>  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d1666-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d1666-105">Methods</span></span>  
 <span data-ttu-id="d1666-106">Die OperationBehaviorAttribute-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="d1666-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d1666-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d1666-107">Properties</span></span>  
 <span data-ttu-id="d1666-108">Die OperationBehaviorAttribute-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d1666-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="d1666-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="d1666-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="d1666-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d1666-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="d1666-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d1666-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1666-112">Der Zustand der Funktion für automatisches Verwerfen für Parameter.</span><span class="sxs-lookup"><span data-stu-id="d1666-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="d1666-113">Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="d1666-113">Impersonation</span></span>  
 <span data-ttu-id="d1666-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d1666-114">Data type: string</span></span>  
  
 <span data-ttu-id="d1666-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d1666-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1666-116">Gibt die Ebene des Aufruferidentitätswechsels an, die von dem Vorgang unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d1666-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="d1666-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="d1666-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="d1666-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d1666-118">Data type: string</span></span>  
  
 <span data-ttu-id="d1666-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d1666-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1666-120">Gibt an, wann das Objekt im Verlauf eines Vorgangsaufrufs wiederverwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d1666-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="d1666-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="d1666-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="d1666-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d1666-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="d1666-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d1666-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1666-124">Gibt an, ob die aktuelle Transaktion automatisch übergeben werden soll, wenn keine unbehandelten Ausnahmen auftreten.</span><span class="sxs-lookup"><span data-stu-id="d1666-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="d1666-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="d1666-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="d1666-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d1666-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="d1666-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d1666-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d1666-128">Gibt an, ob der Vorgang eine Transaktion erfordert.</span><span class="sxs-lookup"><span data-stu-id="d1666-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1666-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1666-129">Requirements</span></span>  
  
|<span data-ttu-id="d1666-130">MOF</span><span class="sxs-lookup"><span data-stu-id="d1666-130">MOF</span></span>|<span data-ttu-id="d1666-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d1666-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d1666-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="d1666-132">Namespace</span></span>|<span data-ttu-id="d1666-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d1666-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1666-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1666-134">See also</span></span>
- <xref:System.ServiceModel.OperationBehaviorAttribute>
