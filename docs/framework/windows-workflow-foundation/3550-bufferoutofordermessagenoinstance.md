---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 1af943e23aa643c6614b946175c0b1854a7ceb62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755583"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="82c0f-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="82c0f-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="82c0f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="82c0f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82c0f-104">ID</span><span class="sxs-lookup"><span data-stu-id="82c0f-104">ID</span></span>|<span data-ttu-id="82c0f-105">3550</span><span class="sxs-lookup"><span data-stu-id="82c0f-105">3550</span></span>|  
|<span data-ttu-id="82c0f-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82c0f-106">Keywords</span></span>|<span data-ttu-id="82c0f-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="82c0f-107">WFServices</span></span>|  
|<span data-ttu-id="82c0f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="82c0f-108">Level</span></span>|<span data-ttu-id="82c0f-109">Information</span><span class="sxs-lookup"><span data-stu-id="82c0f-109">Information</span></span>|  
|<span data-ttu-id="82c0f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="82c0f-110">Channel</span></span>|<span data-ttu-id="82c0f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="82c0f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="82c0f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82c0f-112">Description</span></span>  
 <span data-ttu-id="82c0f-113">Gibt an, dass ein gepufferter Empfang fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="82c0f-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="82c0f-114">Der Vorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="82c0f-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="82c0f-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="82c0f-115">Message</span></span>  
 <span data-ttu-id="82c0f-116">Vorgang '%1' kann derzeit nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="82c0f-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="82c0f-117">Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="82c0f-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="82c0f-118">Details</span><span class="sxs-lookup"><span data-stu-id="82c0f-118">Details</span></span>  
  
|<span data-ttu-id="82c0f-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="82c0f-119">Data Item Name</span></span>|<span data-ttu-id="82c0f-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="82c0f-120">Data Item Type</span></span>|<span data-ttu-id="82c0f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82c0f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="82c0f-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="82c0f-122">OperationName</span></span>|<span data-ttu-id="82c0f-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="82c0f-123">xs:string</span></span>|<span data-ttu-id="82c0f-124">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="82c0f-124">The name of the operation.</span></span>|  
|<span data-ttu-id="82c0f-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="82c0f-125">AppDomain</span></span>|<span data-ttu-id="82c0f-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="82c0f-126">xs:string</span></span>|<span data-ttu-id="82c0f-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="82c0f-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
