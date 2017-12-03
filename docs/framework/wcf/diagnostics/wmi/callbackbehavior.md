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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c10d9e26f86fa569b1a607c9b755f32ee97792a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="callbackbehavior"></a><span data-ttu-id="27440-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="27440-102">CallbackBehavior</span></span>
<span data-ttu-id="27440-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="27440-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27440-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27440-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="27440-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="27440-105">Methods</span></span>  
 <span data-ttu-id="27440-106">Die Klasse CallbackBehavior definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="27440-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="27440-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="27440-107">Properties</span></span>  
 <span data-ttu-id="27440-108">Die Klasse CallbackBehavior verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="27440-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="27440-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="27440-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="27440-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="27440-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="27440-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="27440-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27440-112">Bei true wird die Sitzung automatisch geschlossen, wenn ein Dienst eine Duplexsitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="27440-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="27440-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="27440-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="27440-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="27440-114">Data type: string</span></span>  
<span data-ttu-id="27440-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="27440-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27440-116">Gibt an, ob der Dienst einen Thread, mehrere Threads oder wiedereintrittsfähige Aufrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="27440-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="27440-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="27440-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="27440-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="27440-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="27440-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="27440-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27440-120">Ein Wert, der angibt, ob unbekannte Serialisierungsdaten auf das Kabel gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="27440-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="27440-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="27440-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="27440-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="27440-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="27440-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="27440-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27440-124">Bei Aktivierung werden den Fehlern, die an den Dienst zurückgegeben werden, Details über Ausnahmen des Rückrufs angefügt.</span><span class="sxs-lookup"><span data-stu-id="27440-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="27440-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="27440-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="27440-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="27440-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="27440-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="27440-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27440-128">Die maximale Anzahl von in einem serialisierten Objekt zugelassenen Elementen.</span><span class="sxs-lookup"><span data-stu-id="27440-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="27440-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="27440-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="27440-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="27440-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="27440-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="27440-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27440-132">Gibt an, ob der aktuelle Synchronisierungskontext verwendet werden soll, um den Ausführungsthread auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="27440-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="27440-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="27440-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="27440-134">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="27440-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="27440-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="27440-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27440-136">Legt fest, ob das System oder die Anwendung die Verarbeitung von SOAP MustUnderstand-Headern erzwingt.</span><span class="sxs-lookup"><span data-stu-id="27440-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27440-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27440-137">Requirements</span></span>  
  
|<span data-ttu-id="27440-138">MOF</span><span class="sxs-lookup"><span data-stu-id="27440-138">MOF</span></span>|<span data-ttu-id="27440-139">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="27440-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="27440-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="27440-140">Namespace</span></span>|<span data-ttu-id="27440-141">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="27440-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27440-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27440-142">See Also</span></span>  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
