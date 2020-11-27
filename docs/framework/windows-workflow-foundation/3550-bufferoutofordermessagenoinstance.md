---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 61605d666911cce277bcebbb0a2f803e9a5dcfeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261305"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="da5a5-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="da5a5-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>

## <a name="properties"></a><span data-ttu-id="da5a5-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="da5a5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da5a5-104">id</span><span class="sxs-lookup"><span data-stu-id="da5a5-104">ID</span></span>|<span data-ttu-id="da5a5-105">3550</span><span class="sxs-lookup"><span data-stu-id="da5a5-105">3550</span></span>|  
|<span data-ttu-id="da5a5-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="da5a5-106">Keywords</span></span>|<span data-ttu-id="da5a5-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="da5a5-107">WFServices</span></span>|  
|<span data-ttu-id="da5a5-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="da5a5-108">Level</span></span>|<span data-ttu-id="da5a5-109">Information</span><span class="sxs-lookup"><span data-stu-id="da5a5-109">Information</span></span>|  
|<span data-ttu-id="da5a5-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="da5a5-110">Channel</span></span>|<span data-ttu-id="da5a5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="da5a5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="da5a5-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da5a5-112">Description</span></span>  

 <span data-ttu-id="da5a5-113">Gibt an, dass ein gepufferter Empfang fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="da5a5-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="da5a5-114">Der Vorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="da5a5-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="da5a5-115">`Message`</span><span class="sxs-lookup"><span data-stu-id="da5a5-115">Message</span></span>  

 <span data-ttu-id="da5a5-116">Vorgang '%1' kann derzeit nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="da5a5-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="da5a5-117">Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="da5a5-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="da5a5-118">Details</span><span class="sxs-lookup"><span data-stu-id="da5a5-118">Details</span></span>  
  
|<span data-ttu-id="da5a5-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="da5a5-119">Data Item Name</span></span>|<span data-ttu-id="da5a5-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="da5a5-120">Data Item Type</span></span>|<span data-ttu-id="da5a5-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da5a5-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="da5a5-122">Vorgangsname</span><span class="sxs-lookup"><span data-stu-id="da5a5-122">OperationName</span></span>|<span data-ttu-id="da5a5-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="da5a5-123">xs:string</span></span>|<span data-ttu-id="da5a5-124">Der Name des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="da5a5-124">The name of the operation.</span></span>|  
|<span data-ttu-id="da5a5-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="da5a5-125">AppDomain</span></span>|<span data-ttu-id="da5a5-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="da5a5-126">xs:string</span></span>|<span data-ttu-id="da5a5-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="da5a5-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
