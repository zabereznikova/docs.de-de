---
title: ServiceDebugBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af2dbd9e06876622b57379e17dbb4503cddbaac1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="ef2c5-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="ef2c5-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="ef2c5-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="ef2c5-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef2c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef2c5-104">Syntax</span></span>  
  
```  
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ef2c5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ef2c5-105">Methods</span></span>  
 <span data-ttu-id="ef2c5-106">Die ServiceDebugBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="ef2c5-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ef2c5-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ef2c5-107">Properties</span></span>  
 <span data-ttu-id="ef2c5-108">Die ServiceDebugBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ef2c5-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="ef2c5-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="ef2c5-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="ef2c5-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="ef2c5-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="ef2c5-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ef2c5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef2c5-112">Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="ef2c5-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="ef2c5-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="ef2c5-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="ef2c5-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ef2c5-114">Data type: string</span></span>  
  
 <span data-ttu-id="ef2c5-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ef2c5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef2c5-116">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="ef2c5-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="ef2c5-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="ef2c5-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="ef2c5-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="ef2c5-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="ef2c5-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ef2c5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef2c5-120">Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="ef2c5-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="ef2c5-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="ef2c5-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="ef2c5-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ef2c5-122">Data type: string</span></span>  
  
 <span data-ttu-id="ef2c5-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ef2c5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef2c5-124">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="ef2c5-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="ef2c5-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="ef2c5-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="ef2c5-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="ef2c5-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="ef2c5-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ef2c5-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef2c5-128">Gibt an, ob verwaltete Ausnahmeinformationen in Details der SOAP-Fehler für Debugzwecke an die Clients zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ef2c5-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef2c5-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef2c5-129">Requirements</span></span>  
  
|<span data-ttu-id="ef2c5-130">MOF</span><span class="sxs-lookup"><span data-stu-id="ef2c5-130">MOF</span></span>|<span data-ttu-id="ef2c5-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ef2c5-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ef2c5-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="ef2c5-132">Namespace</span></span>|<span data-ttu-id="ef2c5-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ef2c5-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef2c5-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef2c5-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>
