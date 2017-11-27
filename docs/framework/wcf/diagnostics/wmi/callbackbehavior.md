---
title: CallbackBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9df9629e280a2aec6acf93773e09384e763280ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="callbackbehavior"></a><span data-ttu-id="7929d-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="7929d-102">CallbackBehavior</span></span>
<span data-ttu-id="7929d-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="7929d-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7929d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7929d-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="7929d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7929d-105">Methods</span></span>  
 <span data-ttu-id="7929d-106">Die Klasse CallbackBehavior definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="7929d-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7929d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7929d-107">Properties</span></span>  
 <span data-ttu-id="7929d-108">Die Klasse CallbackBehavior verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="7929d-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="7929d-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="7929d-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="7929d-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="7929d-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="7929d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7929d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7929d-112">Bei true wird die Sitzung automatisch geschlossen, wenn ein Dienst eine Duplexsitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="7929d-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="7929d-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="7929d-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="7929d-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7929d-114">Data type: string</span></span>  
<span data-ttu-id="7929d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7929d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7929d-116">Gibt an, ob der Dienst einen Thread, mehrere Threads oder wiedereintrittsfähige Aufrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7929d-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="7929d-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="7929d-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="7929d-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="7929d-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="7929d-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7929d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7929d-120">Ein Wert, der angibt, ob unbekannte Serialisierungsdaten auf das Kabel gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7929d-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="7929d-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="7929d-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="7929d-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="7929d-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="7929d-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7929d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7929d-124">Bei Aktivierung werden den Fehlern, die an den Dienst zurückgegeben werden, Details über Ausnahmen des Rückrufs angefügt.</span><span class="sxs-lookup"><span data-stu-id="7929d-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="7929d-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="7929d-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="7929d-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="7929d-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="7929d-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7929d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7929d-128">Die maximale Anzahl von in einem serialisierten Objekt zugelassenen Elementen.</span><span class="sxs-lookup"><span data-stu-id="7929d-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="7929d-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="7929d-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="7929d-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="7929d-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="7929d-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7929d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7929d-132">Gibt an, ob der aktuelle Synchronisierungskontext verwendet werden soll, um den Ausführungsthread auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7929d-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="7929d-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="7929d-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="7929d-134">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="7929d-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="7929d-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7929d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7929d-136">Legt fest, ob das System oder die Anwendung die Verarbeitung von SOAP MustUnderstand-Headern erzwingt.</span><span class="sxs-lookup"><span data-stu-id="7929d-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7929d-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7929d-137">Requirements</span></span>  
  
|<span data-ttu-id="7929d-138">MOF</span><span class="sxs-lookup"><span data-stu-id="7929d-138">MOF</span></span>|<span data-ttu-id="7929d-139">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7929d-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7929d-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="7929d-140">Namespace</span></span>|<span data-ttu-id="7929d-141">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7929d-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7929d-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7929d-142">See Also</span></span>  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
