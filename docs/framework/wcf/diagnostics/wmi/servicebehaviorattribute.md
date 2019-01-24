---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: 420686ebda7f23a5d883deece251b034147fafa4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654580"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="a888f-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="a888f-102">ServiceBehaviorAttribute</span></span>
<span data-ttu-id="a888f-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="a888f-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a888f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a888f-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a888f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a888f-105">Methods</span></span>  
 <span data-ttu-id="a888f-106">Die ServiceBehaviorAttribute-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="a888f-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a888f-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a888f-107">Properties</span></span>  
 <span data-ttu-id="a888f-108">Die ServiceBehaviorAttribute-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a888f-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="a888f-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="a888f-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="a888f-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a888f-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="a888f-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-112">Gibt an, ob eine Sitzung automatisch geschlossen werden soll, wenn ein Client eine Ausgabesitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="a888f-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="a888f-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="a888f-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="a888f-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a888f-114">Data type: string</span></span>  
<span data-ttu-id="a888f-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-116">Gibt an, ob ein Dienst einen Thread, mehrere Threads oder wiedereintrittsfähige Aufrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a888f-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="a888f-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="a888f-117">ConfigurationName</span></span>  
 <span data-ttu-id="a888f-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a888f-118">Data type: string</span></span>  
  
 <span data-ttu-id="a888f-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-120">Der Name der Dienstkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a888f-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="a888f-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="a888f-121">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="a888f-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a888f-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="a888f-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-124">Gibt an, ob unbekannte Serialisierungsdaten gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a888f-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="a888f-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="a888f-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="a888f-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a888f-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="a888f-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-128">Gibt an, ob verwaltete Ausnahmeinformationen in Details der SOAP-Fehler für Debugzwecke an die Clients zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a888f-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="a888f-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="a888f-129">InstanceContextMode</span></span>  
 <span data-ttu-id="a888f-130">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a888f-130">Data type: string</span></span>  
  
 <span data-ttu-id="a888f-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-132">Gibt an, wann ein neues Dienstobjekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a888f-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="a888f-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="a888f-133">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="a888f-134">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a888f-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="a888f-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-136">Die maximale Anzahl von in einem serialisierten Objekt zugelassenen Elementen.</span><span class="sxs-lookup"><span data-stu-id="a888f-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="a888f-137">name</span><span class="sxs-lookup"><span data-stu-id="a888f-137">Name</span></span>  
 <span data-ttu-id="a888f-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a888f-138">Data type: string</span></span>  
  
 <span data-ttu-id="a888f-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-140">Das Namensattribut des Diensts in WSDL.</span><span class="sxs-lookup"><span data-stu-id="a888f-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="a888f-141">Namespace</span><span class="sxs-lookup"><span data-stu-id="a888f-141">Namespace</span></span>  
 <span data-ttu-id="a888f-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a888f-142">Data type: string</span></span>  
  
 <span data-ttu-id="a888f-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-144">Der Zielnamespace des Diensts in WSDL.</span><span class="sxs-lookup"><span data-stu-id="a888f-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="a888f-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="a888f-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  
 <span data-ttu-id="a888f-146">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a888f-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="a888f-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-148">Gibt an, ob das Dienstobjekt wiederverwendet wird, wenn die aktuelle Transaktion abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="a888f-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="a888f-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="a888f-149">TransactionAutoCompleteOnSessionClose</span></span>  
 <span data-ttu-id="a888f-150">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a888f-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="a888f-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-152">Gibt an, ob ausstehende Transaktionen abgeschlossen werden, wenn die aktuelle Sitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="a888f-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="a888f-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="a888f-153">TransactionIsolationLevel</span></span>  
 <span data-ttu-id="a888f-154">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a888f-154">Data type: string</span></span>  
  
 <span data-ttu-id="a888f-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-156">Gibt die Isolationsstufe für die Transaktion an.</span><span class="sxs-lookup"><span data-stu-id="a888f-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="a888f-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="a888f-157">TransactionTimeout</span></span>  
 <span data-ttu-id="a888f-158">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="a888f-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="a888f-159">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-160">Der Zeitraum, in dem eine Transaktion abgeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="a888f-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="a888f-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="a888f-161">UseSynchronizationContext</span></span>  
 <span data-ttu-id="a888f-162">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a888f-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="a888f-163">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-164">Gibt an, ob der aktuelle Synchronisierungskontext zur Auswahl der Threadausführung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a888f-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="a888f-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="a888f-165">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="a888f-166">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a888f-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="a888f-167">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a888f-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a888f-168">Legt fest, ob das System oder die Anwendung die Verarbeitung von SOAP MustUnderstand-Headern erzwingt.</span><span class="sxs-lookup"><span data-stu-id="a888f-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a888f-169">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a888f-169">Requirements</span></span>  
  
|<span data-ttu-id="a888f-170">MOF</span><span class="sxs-lookup"><span data-stu-id="a888f-170">MOF</span></span>|<span data-ttu-id="a888f-171">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a888f-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a888f-172">Namespace</span><span class="sxs-lookup"><span data-stu-id="a888f-172">Namespace</span></span>|<span data-ttu-id="a888f-173">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a888f-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a888f-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a888f-174">See also</span></span>
- <xref:System.ServiceModel.ServiceBehaviorAttribute>
