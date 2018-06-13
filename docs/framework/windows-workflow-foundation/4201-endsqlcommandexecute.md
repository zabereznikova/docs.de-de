---
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 75c1cdd10aca6b177911bd9d2f51468016eb9e15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510220"
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="0bf60-102">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="0bf60-102">4201 - EndSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="0bf60-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0bf60-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0bf60-104">ID</span><span class="sxs-lookup"><span data-stu-id="0bf60-104">ID</span></span>|<span data-ttu-id="0bf60-105">4201</span><span class="sxs-lookup"><span data-stu-id="0bf60-105">4201</span></span>|  
|<span data-ttu-id="0bf60-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0bf60-106">Keywords</span></span>|<span data-ttu-id="0bf60-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="0bf60-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="0bf60-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="0bf60-108">Level</span></span>|<span data-ttu-id="0bf60-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="0bf60-109">Verbose</span></span>|  
|<span data-ttu-id="0bf60-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="0bf60-110">Channel</span></span>|<span data-ttu-id="0bf60-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0bf60-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0bf60-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bf60-112">Description</span></span>  
 <span data-ttu-id="0bf60-113">Gibt an, dass ein SQL-Befehl beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="0bf60-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0bf60-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="0bf60-114">Message</span></span>  
 <span data-ttu-id="0bf60-115">Ausführung des SQL-Befehls beenden: %1</span><span class="sxs-lookup"><span data-stu-id="0bf60-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="0bf60-116">Details</span><span class="sxs-lookup"><span data-stu-id="0bf60-116">Details</span></span>  
  
|<span data-ttu-id="0bf60-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="0bf60-117">Data Item Name</span></span>|<span data-ttu-id="0bf60-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="0bf60-118">Data Item Type</span></span>|<span data-ttu-id="0bf60-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bf60-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0bf60-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="0bf60-120">SqlCommand</span></span>|<span data-ttu-id="0bf60-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0bf60-121">xs:string</span></span>|<span data-ttu-id="0bf60-122">Der SQL-Befehl, der ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="0bf60-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="0bf60-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0bf60-123">AppDomain</span></span>|<span data-ttu-id="0bf60-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0bf60-124">xs:string</span></span>|<span data-ttu-id="0bf60-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0bf60-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
