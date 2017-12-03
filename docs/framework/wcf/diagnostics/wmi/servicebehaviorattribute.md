---
title: ServiceBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0a3bc0116ec34a3370012472c31a9191cf26f720
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="19b69-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="19b69-102">ServiceBehaviorAttribute</span></span>
<span data-ttu-id="19b69-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="19b69-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19b69-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19b69-104">Syntax</span></span>  
  
```  
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="19b69-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="19b69-105">Methods</span></span>  
 <span data-ttu-id="19b69-106">Die ServiceBehaviorAttribute-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="19b69-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="19b69-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="19b69-107">Properties</span></span>  
 <span data-ttu-id="19b69-108">Die ServiceBehaviorAttribute-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="19b69-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="19b69-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="19b69-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="19b69-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="19b69-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="19b69-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-112">Gibt an, ob eine Sitzung automatisch geschlossen werden soll, wenn ein Client eine Ausgabesitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="19b69-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="19b69-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="19b69-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="19b69-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="19b69-114">Data type: string</span></span>  
<span data-ttu-id="19b69-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-116">Gibt an, ob ein Dienst einen Thread, mehrere Threads oder wiedereintrittsfähige Aufrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19b69-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="19b69-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="19b69-117">ConfigurationName</span></span>  
 <span data-ttu-id="19b69-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="19b69-118">Data type: string</span></span>  
  
 <span data-ttu-id="19b69-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-120">Der Name der Dienstkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="19b69-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="19b69-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="19b69-121">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="19b69-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="19b69-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="19b69-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-124">Gibt an, ob unbekannte Serialisierungsdaten gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="19b69-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="19b69-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="19b69-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="19b69-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="19b69-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="19b69-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-128">Gibt an, ob verwaltete Ausnahmeinformationen in Details der SOAP-Fehler für Debugzwecke an die Clients zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="19b69-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="19b69-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="19b69-129">InstanceContextMode</span></span>  
 <span data-ttu-id="19b69-130">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="19b69-130">Data type: string</span></span>  
  
 <span data-ttu-id="19b69-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-132">Gibt an, wann ein neues Dienstobjekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="19b69-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="19b69-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="19b69-133">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="19b69-134">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="19b69-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="19b69-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-136">Die maximale Anzahl von in einem serialisierten Objekt zugelassenen Elementen.</span><span class="sxs-lookup"><span data-stu-id="19b69-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="19b69-137">Name</span><span class="sxs-lookup"><span data-stu-id="19b69-137">Name</span></span>  
 <span data-ttu-id="19b69-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="19b69-138">Data type: string</span></span>  
  
 <span data-ttu-id="19b69-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-140">Das Namensattribut des Diensts in WSDL.</span><span class="sxs-lookup"><span data-stu-id="19b69-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="19b69-141">Namespace</span><span class="sxs-lookup"><span data-stu-id="19b69-141">Namespace</span></span>  
 <span data-ttu-id="19b69-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="19b69-142">Data type: string</span></span>  
  
 <span data-ttu-id="19b69-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-144">Der Zielnamespace des Diensts in WSDL.</span><span class="sxs-lookup"><span data-stu-id="19b69-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="19b69-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="19b69-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  
 <span data-ttu-id="19b69-146">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="19b69-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="19b69-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-148">Gibt an, ob das Dienstobjekt wiederverwendet wird, wenn die aktuelle Transaktion abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="19b69-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="19b69-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="19b69-149">TransactionAutoCompleteOnSessionClose</span></span>  
 <span data-ttu-id="19b69-150">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="19b69-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="19b69-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-152">Gibt an, ob ausstehende Transaktionen abgeschlossen werden, wenn die aktuelle Sitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="19b69-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="19b69-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="19b69-153">TransactionIsolationLevel</span></span>  
 <span data-ttu-id="19b69-154">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="19b69-154">Data type: string</span></span>  
  
 <span data-ttu-id="19b69-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-156">Gibt die Isolationsstufe für die Transaktion an.</span><span class="sxs-lookup"><span data-stu-id="19b69-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="19b69-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="19b69-157">TransactionTimeout</span></span>  
 <span data-ttu-id="19b69-158">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="19b69-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="19b69-159">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-160">Der Zeitraum, in dem eine Transaktion abgeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="19b69-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="19b69-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="19b69-161">UseSynchronizationContext</span></span>  
 <span data-ttu-id="19b69-162">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="19b69-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="19b69-163">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-164">Gibt an, ob der aktuelle Synchronisierungskontext zur Auswahl der Threadausführung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="19b69-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="19b69-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="19b69-165">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="19b69-166">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="19b69-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="19b69-167">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19b69-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b69-168">Legt fest, ob das System oder die Anwendung die Verarbeitung von SOAP MustUnderstand-Headern erzwingt.</span><span class="sxs-lookup"><span data-stu-id="19b69-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19b69-169">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19b69-169">Requirements</span></span>  
  
|<span data-ttu-id="19b69-170">MOF</span><span class="sxs-lookup"><span data-stu-id="19b69-170">MOF</span></span>|<span data-ttu-id="19b69-171">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="19b69-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="19b69-172">Namespace</span><span class="sxs-lookup"><span data-stu-id="19b69-172">Namespace</span></span>|<span data-ttu-id="19b69-173">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="19b69-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19b69-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19b69-174">See Also</span></span>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>
