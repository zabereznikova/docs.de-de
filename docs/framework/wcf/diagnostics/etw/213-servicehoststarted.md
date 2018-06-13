---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 819efa2e13c94e2c7a16c24f6ba9c7ef2b87ef8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458473"
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="219db-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="219db-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="219db-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="219db-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="219db-104">Id</span><span class="sxs-lookup"><span data-stu-id="219db-104">ID</span></span>|<span data-ttu-id="219db-105">213</span><span class="sxs-lookup"><span data-stu-id="219db-105">213</span></span>|  
|<span data-ttu-id="219db-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="219db-106">Keywords</span></span>|<span data-ttu-id="219db-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="219db-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="219db-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="219db-108">Level</span></span>|<span data-ttu-id="219db-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="219db-109">LogAlways</span></span>|  
|<span data-ttu-id="219db-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="219db-110">Channel</span></span>|<span data-ttu-id="219db-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="219db-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="219db-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="219db-112">Description</span></span>  
 <span data-ttu-id="219db-113">Dieses Ereignis wird ausgegeben, wenn ein im Web gehosteter Diensthost gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="219db-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="219db-114">Dies kommt in der Regel vor, wenn der Dienst von einer Nachricht aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="219db-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="219db-115">Es kann auch vorkommen, wenn für den Dienst das automatische Starten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="219db-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="219db-116">Meldung</span><span class="sxs-lookup"><span data-stu-id="219db-116">Message</span></span>  
 <span data-ttu-id="219db-117">ServiceHost wurde gestartet: '%1'.</span><span class="sxs-lookup"><span data-stu-id="219db-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="219db-118">Details</span><span class="sxs-lookup"><span data-stu-id="219db-118">Details</span></span>  
  
|<span data-ttu-id="219db-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="219db-119">Data Item Name</span></span>|<span data-ttu-id="219db-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="219db-120">Data Item Type</span></span>|<span data-ttu-id="219db-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="219db-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="219db-122">Service Type Name</span><span class="sxs-lookup"><span data-stu-id="219db-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="219db-123">Der CLR-FullName des Typs der Dienstimplementierung.</span><span class="sxs-lookup"><span data-stu-id="219db-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="219db-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="219db-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="219db-125">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="219db-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="219db-126">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="219db-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="219db-127">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="219db-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="219db-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="219db-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="219db-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="219db-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
