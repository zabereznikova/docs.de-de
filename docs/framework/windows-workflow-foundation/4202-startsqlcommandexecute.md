---
title: 4202 - StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: 09e079864369115c773c58c451fc5e0a33a3ae9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774373"
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="cb36e-102">4202 - StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="cb36e-102">4202 - StartSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="cb36e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb36e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb36e-104">ID</span><span class="sxs-lookup"><span data-stu-id="cb36e-104">ID</span></span>|<span data-ttu-id="cb36e-105">4202</span><span class="sxs-lookup"><span data-stu-id="cb36e-105">4202</span></span>|  
|<span data-ttu-id="cb36e-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="cb36e-106">Keywords</span></span>|<span data-ttu-id="cb36e-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="cb36e-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="cb36e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="cb36e-108">Level</span></span>|<span data-ttu-id="cb36e-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="cb36e-109">Verbose</span></span>|  
|<span data-ttu-id="cb36e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="cb36e-110">Channel</span></span>|<span data-ttu-id="cb36e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="cb36e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cb36e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb36e-112">Description</span></span>  
 <span data-ttu-id="cb36e-113">Gibt an, dass ein SQL-Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cb36e-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cb36e-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="cb36e-114">Message</span></span>  
 <span data-ttu-id="cb36e-115">Ausführung des SQL-Befehls wird gestartet: %1</span><span class="sxs-lookup"><span data-stu-id="cb36e-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="cb36e-116">Details</span><span class="sxs-lookup"><span data-stu-id="cb36e-116">Details</span></span>  
  
|<span data-ttu-id="cb36e-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="cb36e-117">Data Item Name</span></span>|<span data-ttu-id="cb36e-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="cb36e-118">Data Item Type</span></span>|<span data-ttu-id="cb36e-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb36e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cb36e-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="cb36e-120">SqlCommand</span></span>|<span data-ttu-id="cb36e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb36e-121">xs:string</span></span>|<span data-ttu-id="cb36e-122">Der SQL-Befehl, der ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb36e-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="cb36e-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cb36e-123">AppDomain</span></span>|<span data-ttu-id="cb36e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb36e-124">xs:string</span></span>|<span data-ttu-id="cb36e-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="cb36e-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
