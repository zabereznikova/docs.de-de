---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: dba4abd74cdddeb2b641feec5902413fe0704b1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262293"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="96c1f-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="96c1f-102">ServiceDebugBehavior</span></span>

<span data-ttu-id="96c1f-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="96c1f-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c1f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96c1f-104">Syntax</span></span>  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="96c1f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="96c1f-105">Methods</span></span>  

 <span data-ttu-id="96c1f-106">Die ServiceDebugBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="96c1f-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="96c1f-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="96c1f-107">Properties</span></span>  

 <span data-ttu-id="96c1f-108">Die ServiceDebugBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="96c1f-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="96c1f-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="96c1f-109">HttpHelpPageEnabled</span></span>  

 <span data-ttu-id="96c1f-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="96c1f-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="96c1f-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="96c1f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="96c1f-112">Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="96c1f-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="96c1f-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="96c1f-113">HttpHelpPageUrl</span></span>  

 <span data-ttu-id="96c1f-114">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="96c1f-114">Data type: string</span></span>  
  
 <span data-ttu-id="96c1f-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="96c1f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="96c1f-116">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="96c1f-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="96c1f-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="96c1f-117">HttpsHelpPageEnabled</span></span>  

 <span data-ttu-id="96c1f-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="96c1f-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="96c1f-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="96c1f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="96c1f-120">Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="96c1f-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="96c1f-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="96c1f-121">HttpsHelpPageUrl</span></span>  

 <span data-ttu-id="96c1f-122">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="96c1f-122">Data type: string</span></span>  
  
 <span data-ttu-id="96c1f-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="96c1f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="96c1f-124">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="96c1f-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="96c1f-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="96c1f-125">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="96c1f-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="96c1f-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="96c1f-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="96c1f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="96c1f-128">Gibt an, ob verwaltete Ausnahmeinformationen in Details der SOAP-Fehler für Debugzwecke an die Clients zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="96c1f-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96c1f-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96c1f-129">Requirements</span></span>  
  
|<span data-ttu-id="96c1f-130">MOF</span><span class="sxs-lookup"><span data-stu-id="96c1f-130">MOF</span></span>|<span data-ttu-id="96c1f-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="96c1f-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="96c1f-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="96c1f-132">Namespace</span></span>|<span data-ttu-id="96c1f-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="96c1f-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96c1f-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96c1f-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
