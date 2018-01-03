---
title: ICLRMetaHost::ExitProcess-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.ExitProcess
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2407dd8fb4911bd7e6d46c973ebbab836da4f8fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="ab358-102">ICLRMetaHost::ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="ab358-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="ab358-103">Versucht, alle geladenen Laufzeiten ordnungsgemäß herunterzufahren, und klicken Sie dann beendet den Prozess.</span><span class="sxs-lookup"><span data-stu-id="ab358-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="ab358-104">Hat Vorrang vor den [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="ab358-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab358-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab358-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab358-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab358-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="ab358-107">[in] Der Exitcode für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="ab358-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab358-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ab358-108">Return Value</span></span>  
 <span data-ttu-id="ab358-109">Diese Methode gibt nie zurück, damit dessen Rückgabewert nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ab358-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab358-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab358-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab358-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab358-111">Requirements</span></span>  
 <span data-ttu-id="ab358-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab358-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab358-113">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ab358-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ab358-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ab358-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab358-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab358-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab358-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab358-116">See Also</span></span>  
 [<span data-ttu-id="ab358-117">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab358-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="ab358-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="ab358-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
