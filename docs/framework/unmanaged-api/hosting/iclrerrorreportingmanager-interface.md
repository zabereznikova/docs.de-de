---
title: ICLRErrorReportingManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
ms.openlocfilehash: d3816c8a3b6204b053505aa888eb28d696f8990b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677843"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="0cbce-102">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cbce-102">ICLRErrorReportingManager Interface</span></span>

<span data-ttu-id="0cbce-103">Stellt Methoden bereit, die es dem Host ermöglichen, benutzerdefinierte stackdumps für die Fehlerberichterstattung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0cbce-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0cbce-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0cbce-104">Methods</span></span>  
  
|<span data-ttu-id="0cbce-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0cbce-105">Method</span></span>|<span data-ttu-id="0cbce-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0cbce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0cbce-107">BeginCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="0cbce-107">BeginCustomDump Method</span></span>](iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="0cbce-108">Gibt die Konfiguration von benutzerdefinierten stackdumps für die Fehlerberichterstattung an.</span><span class="sxs-lookup"><span data-stu-id="0cbce-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="0cbce-109">EndCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="0cbce-109">EndCustomDump Method</span></span>](iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="0cbce-110">Löscht die benutzerdefinierte Stapel Sicherungs Konfiguration, die durch einen früheren-Aufrufsatz festgelegt wurde `BeginCustomDump` .</span><span class="sxs-lookup"><span data-stu-id="0cbce-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="0cbce-111">GetBucketParametersForCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="0cbce-111">GetBucketParametersForCurrentException Method</span></span>](iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="0cbce-112">Ruft den Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.</span><span class="sxs-lookup"><span data-stu-id="0cbce-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cbce-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cbce-113">Remarks</span></span>  

 <span data-ttu-id="0cbce-114">Die- `BeginCustomDump` Methode legt die benutzerdefinierte Stapel Sicherungs Konfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="0cbce-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="0cbce-115">Die `EndCustomDump` -Methode löscht die benutzerdefinierte Stapel Sicherungs Konfiguration und gibt jeden zugeordneten Zustand frei.</span><span class="sxs-lookup"><span data-stu-id="0cbce-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="0cbce-116">Er sollte aufgerufen werden, nachdem der benutzerdefinierte Dump fertiggestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0cbce-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0cbce-117">Wenn Sie den Vorgang nicht aufzurufen, ist der `EndCustomDump` Speicherfehler</span><span class="sxs-lookup"><span data-stu-id="0cbce-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cbce-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0cbce-118">Requirements</span></span>  

 <span data-ttu-id="0cbce-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cbce-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cbce-120">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="0cbce-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0cbce-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0cbce-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cbce-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cbce-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cbce-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0cbce-123">See also</span></span>

- [<span data-ttu-id="0cbce-124">ECustomDumpItemKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0cbce-124">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="0cbce-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0cbce-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
