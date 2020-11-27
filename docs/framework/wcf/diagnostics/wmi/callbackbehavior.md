---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: cec9005a099247671dbebaacc0b242ca8d7a0144
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269647"
---
# <a name="callbackbehavior"></a><span data-ttu-id="50a4a-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="50a4a-102">CallbackBehavior</span></span>

<span data-ttu-id="50a4a-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="50a4a-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50a4a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50a4a-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="50a4a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="50a4a-105">Methods</span></span>  

 <span data-ttu-id="50a4a-106">Die Klasse CallbackBehavior definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="50a4a-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="50a4a-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="50a4a-107">Properties</span></span>  

 <span data-ttu-id="50a4a-108">Die Klasse CallbackBehavior verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="50a4a-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="50a4a-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="50a4a-109">AutomaticSessionShutdown</span></span>  

 <span data-ttu-id="50a4a-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="50a4a-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="50a4a-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50a4a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50a4a-112">Bei true wird die Sitzung automatisch geschlossen, wenn ein Dienst eine Duplexsitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="50a4a-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="50a4a-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="50a4a-113">ConcurrencyMode</span></span>  

 <span data-ttu-id="50a4a-114">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="50a4a-114">Data type: string</span></span>  
<span data-ttu-id="50a4a-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50a4a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50a4a-116">Gibt an, ob der Dienst einen Thread, mehrere Threads oder wiedereintrittsfähige Aufrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="50a4a-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="50a4a-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="50a4a-117">IgnoreExtensionDataObject</span></span>  

 <span data-ttu-id="50a4a-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="50a4a-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="50a4a-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50a4a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50a4a-120">Ein Wert, der angibt, ob unbekannte Serialisierungsdaten auf das Kabel gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="50a4a-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="50a4a-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="50a4a-121">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="50a4a-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="50a4a-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="50a4a-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50a4a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50a4a-124">Bei Aktivierung werden den Fehlern, die an den Dienst zurückgegeben werden, Details über Ausnahmen des Rückrufs angefügt.</span><span class="sxs-lookup"><span data-stu-id="50a4a-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="50a4a-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="50a4a-125">MaxItemsInObjectGraph</span></span>  

 <span data-ttu-id="50a4a-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="50a4a-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="50a4a-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50a4a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50a4a-128">Die maximale Anzahl von in einem serialisierten Objekt zugelassenen Elementen.</span><span class="sxs-lookup"><span data-stu-id="50a4a-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="50a4a-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="50a4a-129">UseSynchronizationContext</span></span>  

 <span data-ttu-id="50a4a-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="50a4a-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="50a4a-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50a4a-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50a4a-132">Gibt an, ob der aktuelle Synchronisierungskontext verwendet werden soll, um den Ausführungsthread auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="50a4a-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="50a4a-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="50a4a-133">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="50a4a-134">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="50a4a-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="50a4a-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50a4a-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50a4a-136">Legt fest, ob das System oder die Anwendung die Verarbeitung von SOAP MustUnderstand-Headern erzwingt.</span><span class="sxs-lookup"><span data-stu-id="50a4a-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50a4a-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50a4a-137">Requirements</span></span>  
  
|<span data-ttu-id="50a4a-138">MOF</span><span class="sxs-lookup"><span data-stu-id="50a4a-138">MOF</span></span>|<span data-ttu-id="50a4a-139">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="50a4a-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="50a4a-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="50a4a-140">Namespace</span></span>|<span data-ttu-id="50a4a-141">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="50a4a-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50a4a-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50a4a-142">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
