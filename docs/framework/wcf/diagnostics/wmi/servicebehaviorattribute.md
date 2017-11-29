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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f7401acd5aefcb7a8c02ea6c05a94374e41d9b9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="d3967-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="d3967-102">ServiceBehaviorAttribute</span></span>
<span data-ttu-id="d3967-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="d3967-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3967-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3967-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="d3967-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d3967-105">Methods</span></span>  
 <span data-ttu-id="d3967-106">Die ServiceBehaviorAttribute-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="d3967-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d3967-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d3967-107">Properties</span></span>  
 <span data-ttu-id="d3967-108">Die ServiceBehaviorAttribute-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d3967-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="d3967-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="d3967-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="d3967-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d3967-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="d3967-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-112">Gibt an, ob eine Sitzung automatisch geschlossen werden soll, wenn ein Client eine Ausgabesitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="d3967-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="d3967-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="d3967-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="d3967-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d3967-114">Data type: string</span></span>  
<span data-ttu-id="d3967-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-116">Gibt an, ob ein Dienst einen Thread, mehrere Threads oder wiedereintrittsfähige Aufrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d3967-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="d3967-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="d3967-117">ConfigurationName</span></span>  
 <span data-ttu-id="d3967-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d3967-118">Data type: string</span></span>  
  
 <span data-ttu-id="d3967-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-120">Der Name der Dienstkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="d3967-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="d3967-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="d3967-121">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="d3967-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d3967-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="d3967-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-124">Gibt an, ob unbekannte Serialisierungsdaten gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d3967-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="d3967-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="d3967-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="d3967-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d3967-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="d3967-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-128">Gibt an, ob verwaltete Ausnahmeinformationen in Details der SOAP-Fehler für Debugzwecke an die Clients zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d3967-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="d3967-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="d3967-129">InstanceContextMode</span></span>  
 <span data-ttu-id="d3967-130">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d3967-130">Data type: string</span></span>  
  
 <span data-ttu-id="d3967-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-132">Gibt an, wann ein neues Dienstobjekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d3967-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="d3967-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="d3967-133">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="d3967-134">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="d3967-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="d3967-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-136">Die maximale Anzahl von in einem serialisierten Objekt zugelassenen Elementen.</span><span class="sxs-lookup"><span data-stu-id="d3967-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="d3967-137">Name</span><span class="sxs-lookup"><span data-stu-id="d3967-137">Name</span></span>  
 <span data-ttu-id="d3967-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d3967-138">Data type: string</span></span>  
  
 <span data-ttu-id="d3967-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-140">Das Namensattribut des Diensts in WSDL.</span><span class="sxs-lookup"><span data-stu-id="d3967-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="d3967-141">Namespace</span><span class="sxs-lookup"><span data-stu-id="d3967-141">Namespace</span></span>  
 <span data-ttu-id="d3967-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d3967-142">Data type: string</span></span>  
  
 <span data-ttu-id="d3967-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-144">Der Zielnamespace des Diensts in WSDL.</span><span class="sxs-lookup"><span data-stu-id="d3967-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="d3967-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="d3967-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  
 <span data-ttu-id="d3967-146">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d3967-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="d3967-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-148">Gibt an, ob das Dienstobjekt wiederverwendet wird, wenn die aktuelle Transaktion abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d3967-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="d3967-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="d3967-149">TransactionAutoCompleteOnSessionClose</span></span>  
 <span data-ttu-id="d3967-150">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d3967-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="d3967-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-152">Gibt an, ob ausstehende Transaktionen abgeschlossen werden, wenn die aktuelle Sitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="d3967-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="d3967-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="d3967-153">TransactionIsolationLevel</span></span>  
 <span data-ttu-id="d3967-154">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d3967-154">Data type: string</span></span>  
  
 <span data-ttu-id="d3967-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-156">Gibt die Isolationsstufe für die Transaktion an.</span><span class="sxs-lookup"><span data-stu-id="d3967-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="d3967-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="d3967-157">TransactionTimeout</span></span>  
 <span data-ttu-id="d3967-158">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="d3967-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="d3967-159">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-160">Der Zeitraum, in dem eine Transaktion abgeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="d3967-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="d3967-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="d3967-161">UseSynchronizationContext</span></span>  
 <span data-ttu-id="d3967-162">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d3967-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="d3967-163">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-164">Gibt an, ob der aktuelle Synchronisierungskontext zur Auswahl der Threadausführung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d3967-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="d3967-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="d3967-165">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="d3967-166">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="d3967-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="d3967-167">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d3967-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3967-168">Legt fest, ob das System oder die Anwendung die Verarbeitung von SOAP MustUnderstand-Headern erzwingt.</span><span class="sxs-lookup"><span data-stu-id="d3967-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3967-169">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d3967-169">Requirements</span></span>  
  
|<span data-ttu-id="d3967-170">MOF</span><span class="sxs-lookup"><span data-stu-id="d3967-170">MOF</span></span>|<span data-ttu-id="d3967-171">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d3967-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d3967-172">Namespace</span><span class="sxs-lookup"><span data-stu-id="d3967-172">Namespace</span></span>|<span data-ttu-id="d3967-173">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d3967-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3967-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3967-174">See Also</span></span>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>
