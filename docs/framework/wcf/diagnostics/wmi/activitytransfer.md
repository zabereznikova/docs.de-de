---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c1caf0ae27efce858328e5db88434253be61d50
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="99104-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="99104-102">ActivityTransfer</span></span>
<span data-ttu-id="99104-103">Aktivitätsübertragungsereignis</span><span class="sxs-lookup"><span data-stu-id="99104-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99104-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99104-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="99104-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="99104-105">Methods</span></span>  
 <span data-ttu-id="99104-106">Von der ActivityTransfer-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="99104-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="99104-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="99104-107">Properties</span></span>  
 <span data-ttu-id="99104-108">Die ActivityTransfer-Klasse besitzt folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="99104-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="99104-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="99104-109">ActivityID</span></span>  
  
-   <span data-ttu-id="99104-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="99104-110">Data type: object</span></span>  
    <span data-ttu-id="99104-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="99104-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="99104-112">Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="99104-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="99104-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="99104-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="99104-114">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="99104-114">Data type: object</span></span>  
    <span data-ttu-id="99104-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="99104-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="99104-116">Verwandte Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="99104-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99104-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99104-117">Requirements</span></span>  
  
|<span data-ttu-id="99104-118">MOF</span><span class="sxs-lookup"><span data-stu-id="99104-118">MOF</span></span>|<span data-ttu-id="99104-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="99104-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="99104-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="99104-120">Namespace</span></span>|<span data-ttu-id="99104-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="99104-121">Defined in root\ServiceModel.</span></span>|
