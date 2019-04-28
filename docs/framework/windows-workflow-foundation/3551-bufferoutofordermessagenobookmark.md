---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 89643edde5856688c762b0cf0d188bd4e7ba8a24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755531"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="802de-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="802de-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="802de-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="802de-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="802de-104">ID</span><span class="sxs-lookup"><span data-stu-id="802de-104">ID</span></span>|<span data-ttu-id="802de-105">3551</span><span class="sxs-lookup"><span data-stu-id="802de-105">3551</span></span>|  
|<span data-ttu-id="802de-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="802de-106">Keywords</span></span>|<span data-ttu-id="802de-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="802de-107">WFServices</span></span>|  
|<span data-ttu-id="802de-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="802de-108">Level</span></span>|<span data-ttu-id="802de-109">Information</span><span class="sxs-lookup"><span data-stu-id="802de-109">Information</span></span>|  
|<span data-ttu-id="802de-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="802de-110">Channel</span></span>|<span data-ttu-id="802de-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="802de-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="802de-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="802de-112">Description</span></span>  
 <span data-ttu-id="802de-113">Gibt an, dass eine Lesezeichenwiederaufnahme fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="802de-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="802de-114">Der gepufferte Empfangsvorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="802de-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="802de-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="802de-115">Message</span></span>  
 <span data-ttu-id="802de-116">Vorgang '%2' der Dienstinstanz '%1' kann derzeit nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="802de-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="802de-117">Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="802de-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="802de-118">Details</span><span class="sxs-lookup"><span data-stu-id="802de-118">Details</span></span>  
  
|<span data-ttu-id="802de-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="802de-119">Data Item Name</span></span>|<span data-ttu-id="802de-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="802de-120">Data Item Type</span></span>|<span data-ttu-id="802de-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="802de-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="802de-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="802de-122">OperationName</span></span>|<span data-ttu-id="802de-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="802de-123">xs:string</span></span>|<span data-ttu-id="802de-124">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="802de-124">The name of the operation.</span></span>|  
|<span data-ttu-id="802de-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="802de-125">ServiceInstanceId</span></span>|<span data-ttu-id="802de-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="802de-126">xs:string</span></span>|<span data-ttu-id="802de-127">Die ID der Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="802de-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="802de-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="802de-128">AppDomain</span></span>|<span data-ttu-id="802de-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="802de-129">xs:string</span></span>|<span data-ttu-id="802de-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="802de-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
