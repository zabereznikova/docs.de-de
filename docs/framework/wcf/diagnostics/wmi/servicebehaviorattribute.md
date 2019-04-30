---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: b6221e93f10b87a368bd594932a8c36ae14df8f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61957013"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="fb11d-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="fb11d-102">ServiceBehaviorAttribute</span></span>
<span data-ttu-id="fb11d-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="fb11d-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb11d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb11d-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="fb11d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="fb11d-105">Methods</span></span>  
 <span data-ttu-id="fb11d-106">Die ServiceBehaviorAttribute-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="fb11d-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fb11d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fb11d-107">Properties</span></span>  
 <span data-ttu-id="fb11d-108">Die ServiceBehaviorAttribute-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="fb11d-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="fb11d-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="fb11d-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="fb11d-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="fb11d-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="fb11d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-112">Gibt an, ob eine Sitzung automatisch geschlossen werden soll, wenn ein Client eine Ausgabesitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="fb11d-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="fb11d-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="fb11d-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="fb11d-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="fb11d-114">Data type: string</span></span>  
<span data-ttu-id="fb11d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-116">Gibt an, ob ein Dienst einen Thread, mehrere Threads oder wiedereintrittsfähige Aufrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb11d-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="fb11d-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="fb11d-117">ConfigurationName</span></span>  
 <span data-ttu-id="fb11d-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="fb11d-118">Data type: string</span></span>  
  
 <span data-ttu-id="fb11d-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-120">Der Name der Dienstkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="fb11d-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="fb11d-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="fb11d-121">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="fb11d-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="fb11d-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="fb11d-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-124">Gibt an, ob unbekannte Serialisierungsdaten gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fb11d-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="fb11d-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="fb11d-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="fb11d-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="fb11d-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="fb11d-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-128">Gibt an, ob verwaltete Ausnahmeinformationen in Details der SOAP-Fehler für Debugzwecke an die Clients zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fb11d-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="fb11d-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="fb11d-129">InstanceContextMode</span></span>  
 <span data-ttu-id="fb11d-130">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="fb11d-130">Data type: string</span></span>  
  
 <span data-ttu-id="fb11d-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-132">Gibt an, wann ein neues Dienstobjekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fb11d-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="fb11d-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="fb11d-133">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="fb11d-134">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="fb11d-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="fb11d-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-136">Die maximale Anzahl von in einem serialisierten Objekt zugelassenen Elementen.</span><span class="sxs-lookup"><span data-stu-id="fb11d-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="fb11d-137">Name</span><span class="sxs-lookup"><span data-stu-id="fb11d-137">Name</span></span>  
 <span data-ttu-id="fb11d-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="fb11d-138">Data type: string</span></span>  
  
 <span data-ttu-id="fb11d-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-140">Das Namensattribut des Diensts in WSDL.</span><span class="sxs-lookup"><span data-stu-id="fb11d-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="fb11d-141">Namespace</span><span class="sxs-lookup"><span data-stu-id="fb11d-141">Namespace</span></span>  
 <span data-ttu-id="fb11d-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="fb11d-142">Data type: string</span></span>  
  
 <span data-ttu-id="fb11d-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-144">Der Zielnamespace des Diensts in WSDL.</span><span class="sxs-lookup"><span data-stu-id="fb11d-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="fb11d-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="fb11d-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  
 <span data-ttu-id="fb11d-146">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="fb11d-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="fb11d-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-148">Gibt an, ob das Dienstobjekt wiederverwendet wird, wenn die aktuelle Transaktion abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="fb11d-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="fb11d-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="fb11d-149">TransactionAutoCompleteOnSessionClose</span></span>  
 <span data-ttu-id="fb11d-150">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="fb11d-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="fb11d-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-152">Gibt an, ob ausstehende Transaktionen abgeschlossen werden, wenn die aktuelle Sitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="fb11d-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="fb11d-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="fb11d-153">TransactionIsolationLevel</span></span>  
 <span data-ttu-id="fb11d-154">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="fb11d-154">Data type: string</span></span>  
  
 <span data-ttu-id="fb11d-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-156">Gibt die Isolationsstufe für die Transaktion an.</span><span class="sxs-lookup"><span data-stu-id="fb11d-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="fb11d-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="fb11d-157">TransactionTimeout</span></span>  
 <span data-ttu-id="fb11d-158">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="fb11d-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="fb11d-159">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-160">Der Zeitraum, in dem eine Transaktion abgeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="fb11d-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="fb11d-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="fb11d-161">UseSynchronizationContext</span></span>  
 <span data-ttu-id="fb11d-162">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="fb11d-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="fb11d-163">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-164">Gibt an, ob der aktuelle Synchronisierungskontext zur Auswahl der Threadausführung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb11d-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="fb11d-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="fb11d-165">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="fb11d-166">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="fb11d-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="fb11d-167">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fb11d-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11d-168">Legt fest, ob das System oder die Anwendung die Verarbeitung von SOAP MustUnderstand-Headern erzwingt.</span><span class="sxs-lookup"><span data-stu-id="fb11d-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb11d-169">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb11d-169">Requirements</span></span>  
  
|<span data-ttu-id="fb11d-170">MOF</span><span class="sxs-lookup"><span data-stu-id="fb11d-170">MOF</span></span>|<span data-ttu-id="fb11d-171">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fb11d-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fb11d-172">Namespace</span><span class="sxs-lookup"><span data-stu-id="fb11d-172">Namespace</span></span>|<span data-ttu-id="fb11d-173">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fb11d-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb11d-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb11d-174">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
