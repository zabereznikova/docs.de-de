---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 9d8f4335c304d164daafeb0ad4de5b4e3bba4590
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973966"
---
# <a name="callbackbehavior"></a><span data-ttu-id="dc439-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="dc439-102">CallbackBehavior</span></span>
<span data-ttu-id="dc439-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="dc439-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc439-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc439-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="dc439-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="dc439-105">Methods</span></span>  
 <span data-ttu-id="dc439-106">Die Klasse CallbackBehavior definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="dc439-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dc439-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc439-107">Properties</span></span>  
 <span data-ttu-id="dc439-108">Die Klasse CallbackBehavior verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="dc439-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="dc439-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="dc439-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="dc439-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="dc439-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="dc439-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dc439-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc439-112">Bei true wird die Sitzung automatisch geschlossen, wenn ein Dienst eine Duplexsitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="dc439-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="dc439-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="dc439-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="dc439-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="dc439-114">Data type: string</span></span>  
<span data-ttu-id="dc439-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dc439-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc439-116">Gibt an, ob der Dienst einen Thread, mehrere Threads oder wiedereintrittsfähige Aufrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dc439-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="dc439-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="dc439-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="dc439-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="dc439-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="dc439-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dc439-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc439-120">Ein Wert, der angibt, ob unbekannte Serialisierungsdaten auf das Kabel gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dc439-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="dc439-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="dc439-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="dc439-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="dc439-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="dc439-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dc439-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc439-124">Bei Aktivierung werden den Fehlern, die an den Dienst zurückgegeben werden, Details über Ausnahmen des Rückrufs angefügt.</span><span class="sxs-lookup"><span data-stu-id="dc439-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="dc439-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="dc439-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="dc439-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="dc439-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="dc439-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dc439-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc439-128">Die maximale Anzahl von in einem serialisierten Objekt zugelassenen Elementen.</span><span class="sxs-lookup"><span data-stu-id="dc439-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="dc439-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="dc439-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="dc439-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="dc439-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="dc439-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dc439-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc439-132">Gibt an, ob der aktuelle Synchronisierungskontext verwendet werden soll, um den Ausführungsthread auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="dc439-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="dc439-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="dc439-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="dc439-134">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="dc439-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="dc439-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dc439-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc439-136">Legt fest, ob das System oder die Anwendung die Verarbeitung von SOAP MustUnderstand-Headern erzwingt.</span><span class="sxs-lookup"><span data-stu-id="dc439-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc439-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dc439-137">Requirements</span></span>  
  
|<span data-ttu-id="dc439-138">MOF</span><span class="sxs-lookup"><span data-stu-id="dc439-138">MOF</span></span>|<span data-ttu-id="dc439-139">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dc439-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dc439-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="dc439-140">Namespace</span></span>|<span data-ttu-id="dc439-141">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dc439-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc439-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc439-142">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
