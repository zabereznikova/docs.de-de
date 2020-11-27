---
title: 440 - StartSignpostEvent1
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 1e0278d665a961afab21445ab8490e3e5a94987c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293454"
---
# <a name="440---startsignpostevent1"></a><span data-ttu-id="86929-102">440 - StartSignpostEvent1</span><span class="sxs-lookup"><span data-stu-id="86929-102">440 - StartSignpostEvent1</span></span>

## <a name="properties"></a><span data-ttu-id="86929-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="86929-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86929-104">id</span><span class="sxs-lookup"><span data-stu-id="86929-104">ID</span></span>|<span data-ttu-id="86929-105">440</span><span class="sxs-lookup"><span data-stu-id="86929-105">440</span></span>|  
|<span data-ttu-id="86929-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="86929-106">Keywords</span></span>|<span data-ttu-id="86929-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="86929-107">Troubleshooting</span></span>|  
|<span data-ttu-id="86929-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="86929-108">Level</span></span>|<span data-ttu-id="86929-109">Information</span><span class="sxs-lookup"><span data-stu-id="86929-109">Information</span></span>|  
|<span data-ttu-id="86929-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="86929-110">Channel</span></span>|<span data-ttu-id="86929-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="86929-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="86929-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="86929-112">Description</span></span>  

 <span data-ttu-id="86929-113">Gibt in der Aktivitätsablaufverfolgung eine Nachricht an, die das Überschreiten einer Aktivitätsgrenze beim Senden oder Empfangen gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="86929-113">In activity tracing, indicates a message has started crossing an activity boundary in send or receive.</span></span>  
  
## <a name="message"></a><span data-ttu-id="86929-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="86929-114">Message</span></span>  

 <span data-ttu-id="86929-115">Aktivitätsgrenze.</span><span class="sxs-lookup"><span data-stu-id="86929-115">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="86929-116">Details</span><span class="sxs-lookup"><span data-stu-id="86929-116">Details</span></span>  
  
|<span data-ttu-id="86929-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="86929-117">Data Item Name</span></span>|<span data-ttu-id="86929-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="86929-118">Data Item Type</span></span>|<span data-ttu-id="86929-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="86929-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="86929-120">ExtendedData</span><span class="sxs-lookup"><span data-stu-id="86929-120">ExtendedData</span></span>|`xs:string`|<span data-ttu-id="86929-121">Der Name der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="86929-121">The name of the activity.</span></span>|  
|<span data-ttu-id="86929-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="86929-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="86929-123">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="86929-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
