---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 89643edde5856688c762b0cf0d188bd4e7ba8a24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512230"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="5857e-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="5857e-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="5857e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5857e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5857e-104">ID</span><span class="sxs-lookup"><span data-stu-id="5857e-104">ID</span></span>|<span data-ttu-id="5857e-105">3551</span><span class="sxs-lookup"><span data-stu-id="5857e-105">3551</span></span>|  
|<span data-ttu-id="5857e-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5857e-106">Keywords</span></span>|<span data-ttu-id="5857e-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="5857e-107">WFServices</span></span>|  
|<span data-ttu-id="5857e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="5857e-108">Level</span></span>|<span data-ttu-id="5857e-109">Information</span><span class="sxs-lookup"><span data-stu-id="5857e-109">Information</span></span>|  
|<span data-ttu-id="5857e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="5857e-110">Channel</span></span>|<span data-ttu-id="5857e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5857e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5857e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5857e-112">Description</span></span>  
 <span data-ttu-id="5857e-113">Gibt an, dass eine Lesezeichenwiederaufnahme fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="5857e-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="5857e-114">Der gepufferte Empfangsvorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5857e-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5857e-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="5857e-115">Message</span></span>  
 <span data-ttu-id="5857e-116">Vorgang '%2' der Dienstinstanz '%1' kann derzeit nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5857e-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="5857e-117">Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5857e-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5857e-118">Details</span><span class="sxs-lookup"><span data-stu-id="5857e-118">Details</span></span>  
  
|<span data-ttu-id="5857e-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="5857e-119">Data Item Name</span></span>|<span data-ttu-id="5857e-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="5857e-120">Data Item Type</span></span>|<span data-ttu-id="5857e-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5857e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5857e-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="5857e-122">OperationName</span></span>|<span data-ttu-id="5857e-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="5857e-123">xs:string</span></span>|<span data-ttu-id="5857e-124">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="5857e-124">The name of the operation.</span></span>|  
|<span data-ttu-id="5857e-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="5857e-125">ServiceInstanceId</span></span>|<span data-ttu-id="5857e-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="5857e-126">xs:string</span></span>|<span data-ttu-id="5857e-127">Die ID der Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="5857e-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="5857e-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5857e-128">AppDomain</span></span>|<span data-ttu-id="5857e-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="5857e-129">xs:string</span></span>|<span data-ttu-id="5857e-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5857e-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
