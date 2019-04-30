---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d34f6f1ab6af8e06a0f28fb043faf9fe16a8b211
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008615"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="16d17-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="16d17-102">1004 - WorkflowInstanceAborted</span></span>

## <a name="properties"></a><span data-ttu-id="16d17-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="16d17-103">Properties</span></span>

|||
|-|-|
|<span data-ttu-id="16d17-104">ID</span><span class="sxs-lookup"><span data-stu-id="16d17-104">ID</span></span>|<span data-ttu-id="16d17-105">1004</span><span class="sxs-lookup"><span data-stu-id="16d17-105">1004</span></span>|
|<span data-ttu-id="16d17-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="16d17-106">Keywords</span></span>|<span data-ttu-id="16d17-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="16d17-107">WFRuntime</span></span>|
|<span data-ttu-id="16d17-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="16d17-108">Level</span></span>|<span data-ttu-id="16d17-109">Information</span><span class="sxs-lookup"><span data-stu-id="16d17-109">Information</span></span>|
|<span data-ttu-id="16d17-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="16d17-110">Channel</span></span>|<span data-ttu-id="16d17-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="16d17-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|

## <a name="description"></a><span data-ttu-id="16d17-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16d17-112">Description</span></span>

<span data-ttu-id="16d17-113">Gibt an, dass eine Workflowinstanz mit einer Ausnahme abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="16d17-113">Indicates a workflow instance has aborted with an exception.</span></span>

## <a name="message"></a><span data-ttu-id="16d17-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="16d17-114">Message</span></span>

<span data-ttu-id="16d17-115">WorkflowInstance-ID: '%1' wurde mit einer Ausnahme abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="16d17-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>

## <a name="details"></a><span data-ttu-id="16d17-116">Details</span><span class="sxs-lookup"><span data-stu-id="16d17-116">Details</span></span>

|<span data-ttu-id="16d17-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="16d17-117">Data Item Name</span></span>|<span data-ttu-id="16d17-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="16d17-118">Data Item Type</span></span>|<span data-ttu-id="16d17-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16d17-119">Description</span></span>|
|--------------------|--------------------|-----------------|
|<span data-ttu-id="16d17-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="16d17-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="16d17-121">Die Instanz-ID für den Workflow.</span><span class="sxs-lookup"><span data-stu-id="16d17-121">The instance id for the workflow</span></span>|
|<span data-ttu-id="16d17-122">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="16d17-122">Exception</span></span>|`xs:string`|<span data-ttu-id="16d17-123">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="16d17-123">The exception details for the exception</span></span>|
|<span data-ttu-id="16d17-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="16d17-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="16d17-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="16d17-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
