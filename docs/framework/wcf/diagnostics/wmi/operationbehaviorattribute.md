---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 79601308c66abe43dd5a7f72bd2a05b9d2346c2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975155"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="a49c0-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="a49c0-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="a49c0-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="a49c0-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a49c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a49c0-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a49c0-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a49c0-105">Methods</span></span>  
 <span data-ttu-id="a49c0-106">Die OperationBehaviorAttribute-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="a49c0-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a49c0-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a49c0-107">Properties</span></span>  
 <span data-ttu-id="a49c0-108">Die OperationBehaviorAttribute-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a49c0-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="a49c0-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="a49c0-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="a49c0-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a49c0-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="a49c0-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a49c0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a49c0-112">Der Zustand der Funktion für automatisches Verwerfen für Parameter.</span><span class="sxs-lookup"><span data-stu-id="a49c0-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="a49c0-113">Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="a49c0-113">Impersonation</span></span>  
 <span data-ttu-id="a49c0-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a49c0-114">Data type: string</span></span>  
  
 <span data-ttu-id="a49c0-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a49c0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a49c0-116">Gibt die Ebene des Aufruferidentitätswechsels an, die von dem Vorgang unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a49c0-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="a49c0-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="a49c0-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="a49c0-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a49c0-118">Data type: string</span></span>  
  
 <span data-ttu-id="a49c0-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a49c0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a49c0-120">Gibt an, wann das Objekt im Verlauf eines Vorgangsaufrufs wiederverwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a49c0-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="a49c0-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="a49c0-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="a49c0-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a49c0-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="a49c0-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a49c0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a49c0-124">Gibt an, ob die aktuelle Transaktion automatisch übergeben werden soll, wenn keine unbehandelten Ausnahmen auftreten.</span><span class="sxs-lookup"><span data-stu-id="a49c0-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="a49c0-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="a49c0-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="a49c0-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a49c0-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="a49c0-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a49c0-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a49c0-128">Gibt an, ob der Vorgang eine Transaktion erfordert.</span><span class="sxs-lookup"><span data-stu-id="a49c0-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a49c0-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a49c0-129">Requirements</span></span>  
  
|<span data-ttu-id="a49c0-130">MOF</span><span class="sxs-lookup"><span data-stu-id="a49c0-130">MOF</span></span>|<span data-ttu-id="a49c0-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a49c0-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a49c0-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="a49c0-132">Namespace</span></span>|<span data-ttu-id="a49c0-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a49c0-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a49c0-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a49c0-134">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
