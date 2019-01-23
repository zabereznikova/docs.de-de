---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 2854671eaabb37066b57d87a7496183c9e5bba4d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562848"
---
# <a name="callbackbehavior"></a><span data-ttu-id="e8f87-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="e8f87-102">CallbackBehavior</span></span>
<span data-ttu-id="e8f87-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="e8f87-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f87-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8f87-104">Syntax</span></span>  
  
```csharp
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e8f87-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e8f87-105">Methods</span></span>  
 <span data-ttu-id="e8f87-106">Die Klasse CallbackBehavior definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="e8f87-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e8f87-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e8f87-107">Properties</span></span>  
 <span data-ttu-id="e8f87-108">Die Klasse CallbackBehavior verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e8f87-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="e8f87-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="e8f87-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="e8f87-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e8f87-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8f87-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e8f87-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8f87-112">Bei true wird die Sitzung automatisch geschlossen, wenn ein Dienst eine Duplexsitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="e8f87-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="e8f87-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="e8f87-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="e8f87-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e8f87-114">Data type: string</span></span>  
<span data-ttu-id="e8f87-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e8f87-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8f87-116">Gibt an, ob der Dienst einen Thread, mehrere Threads oder wiedereintrittsfähige Aufrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8f87-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="e8f87-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="e8f87-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="e8f87-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e8f87-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8f87-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e8f87-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8f87-120">Ein Wert, der angibt, ob unbekannte Serialisierungsdaten auf das Kabel gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e8f87-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="e8f87-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="e8f87-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="e8f87-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e8f87-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8f87-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e8f87-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8f87-124">Bei Aktivierung werden den Fehlern, die an den Dienst zurückgegeben werden, Details über Ausnahmen des Rückrufs angefügt.</span><span class="sxs-lookup"><span data-stu-id="e8f87-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="e8f87-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="e8f87-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="e8f87-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e8f87-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8f87-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e8f87-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8f87-128">Die maximale Anzahl von in einem serialisierten Objekt zugelassenen Elementen.</span><span class="sxs-lookup"><span data-stu-id="e8f87-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="e8f87-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="e8f87-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="e8f87-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e8f87-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8f87-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e8f87-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8f87-132">Gibt an, ob der aktuelle Synchronisierungskontext verwendet werden soll, um den Ausführungsthread auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e8f87-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="e8f87-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="e8f87-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="e8f87-134">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e8f87-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8f87-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e8f87-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8f87-136">Legt fest, ob das System oder die Anwendung die Verarbeitung von SOAP MustUnderstand-Headern erzwingt.</span><span class="sxs-lookup"><span data-stu-id="e8f87-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8f87-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8f87-137">Requirements</span></span>  
  
|<span data-ttu-id="e8f87-138">MOF</span><span class="sxs-lookup"><span data-stu-id="e8f87-138">MOF</span></span>|<span data-ttu-id="e8f87-139">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e8f87-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e8f87-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="e8f87-140">Namespace</span></span>|<span data-ttu-id="e8f87-141">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e8f87-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8f87-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8f87-142">See also</span></span>
- <xref:System.ServiceModel.CallbackBehaviorAttribute>
