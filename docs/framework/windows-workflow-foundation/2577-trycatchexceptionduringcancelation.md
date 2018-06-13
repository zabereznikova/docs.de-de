---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: c272dd91249dfc90e6f4c38a7339919a5a6446e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510723"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="70e7f-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="70e7f-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="70e7f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="70e7f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70e7f-104">ID</span><span class="sxs-lookup"><span data-stu-id="70e7f-104">ID</span></span>|<span data-ttu-id="70e7f-105">2577</span><span class="sxs-lookup"><span data-stu-id="70e7f-105">2577</span></span>|  
|<span data-ttu-id="70e7f-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="70e7f-106">Keywords</span></span>|<span data-ttu-id="70e7f-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="70e7f-107">WFActivities</span></span>|  
|<span data-ttu-id="70e7f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="70e7f-108">Level</span></span>|<span data-ttu-id="70e7f-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="70e7f-109">Warning</span></span>|  
|<span data-ttu-id="70e7f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="70e7f-110">Channel</span></span>|<span data-ttu-id="70e7f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="70e7f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="70e7f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70e7f-112">Description</span></span>  
 <span data-ttu-id="70e7f-113">Gibt an, dass eine untergeordnete Aktivität der TryCatch-Aktivität während des Abbruchs eine Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="70e7f-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="70e7f-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="70e7f-114">Message</span></span>  
 <span data-ttu-id="70e7f-115">Eine untergeordnete Aktivität der TryCatch-Aktivität '%1' hat während des Abbruchs eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="70e7f-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="70e7f-116">Details</span><span class="sxs-lookup"><span data-stu-id="70e7f-116">Details</span></span>  
  
|<span data-ttu-id="70e7f-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="70e7f-117">Data Item Name</span></span>|<span data-ttu-id="70e7f-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="70e7f-118">Data Item Type</span></span>|<span data-ttu-id="70e7f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70e7f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="70e7f-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="70e7f-120">DisplayName</span></span>|<span data-ttu-id="70e7f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="70e7f-121">xs:string</span></span>|<span data-ttu-id="70e7f-122">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="70e7f-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="70e7f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="70e7f-123">AppDomain</span></span>|<span data-ttu-id="70e7f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="70e7f-124">xs:string</span></span>|<span data-ttu-id="70e7f-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="70e7f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
