---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 2e38eb2c2d42ffc5436562b254a42215ccabbab2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956961"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="edd90-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="edd90-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="edd90-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="edd90-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edd90-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="edd90-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="edd90-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="edd90-105">Methods</span></span>  
 <span data-ttu-id="edd90-106">Die ServiceDebugBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="edd90-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="edd90-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="edd90-107">Properties</span></span>  
 <span data-ttu-id="edd90-108">Die ServiceDebugBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="edd90-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="edd90-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="edd90-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="edd90-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="edd90-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="edd90-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="edd90-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="edd90-112">Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="edd90-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="edd90-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="edd90-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="edd90-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="edd90-114">Data type: string</span></span>  
  
 <span data-ttu-id="edd90-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="edd90-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="edd90-116">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="edd90-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="edd90-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="edd90-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="edd90-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="edd90-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="edd90-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="edd90-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="edd90-120">Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="edd90-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="edd90-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="edd90-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="edd90-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="edd90-122">Data type: string</span></span>  
  
 <span data-ttu-id="edd90-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="edd90-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="edd90-124">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="edd90-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="edd90-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="edd90-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="edd90-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="edd90-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="edd90-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="edd90-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="edd90-128">Gibt an, ob verwaltete Ausnahmeinformationen in Details der SOAP-Fehler für Debugzwecke an die Clients zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="edd90-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edd90-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="edd90-129">Requirements</span></span>  
  
|<span data-ttu-id="edd90-130">MOF</span><span class="sxs-lookup"><span data-stu-id="edd90-130">MOF</span></span>|<span data-ttu-id="edd90-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="edd90-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="edd90-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="edd90-132">Namespace</span></span>|<span data-ttu-id="edd90-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="edd90-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="edd90-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edd90-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
