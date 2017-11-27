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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: acbc346da940caf933868a03295744132bda4733
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="1bb43-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="1bb43-102">ActivityTransfer</span></span>
<span data-ttu-id="1bb43-103">Aktivitätsübertragungsereignis</span><span class="sxs-lookup"><span data-stu-id="1bb43-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bb43-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1bb43-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1bb43-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1bb43-105">Methods</span></span>  
 <span data-ttu-id="1bb43-106">Von der ActivityTransfer-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="1bb43-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1bb43-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1bb43-107">Properties</span></span>  
 <span data-ttu-id="1bb43-108">Die ActivityTransfer-Klasse besitzt folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1bb43-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="1bb43-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="1bb43-109">ActivityID</span></span>  
  
-   <span data-ttu-id="1bb43-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="1bb43-110">Data type: object</span></span>  
    <span data-ttu-id="1bb43-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1bb43-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="1bb43-112">Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="1bb43-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="1bb43-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="1bb43-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="1bb43-114">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="1bb43-114">Data type: object</span></span>  
    <span data-ttu-id="1bb43-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1bb43-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="1bb43-116">Verwandte Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="1bb43-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bb43-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1bb43-117">Requirements</span></span>  
  
|<span data-ttu-id="1bb43-118">MOF</span><span class="sxs-lookup"><span data-stu-id="1bb43-118">MOF</span></span>|<span data-ttu-id="1bb43-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1bb43-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1bb43-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="1bb43-120">Namespace</span></span>|<span data-ttu-id="1bb43-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1bb43-121">Defined in root\ServiceModel.</span></span>|
