---
title: ICLRMetaHost::ExitProcess-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: d8643c54950486b6374045ff83928c8c7fb568a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140950"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="bda13-102">ICLRMetaHost::ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="bda13-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="bda13-103">Versucht, alle geladenen Laufzeiten ordnungsgemäß herunterzufahren, und beendet dann den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="bda13-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="bda13-104">Ersetzt die [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="bda13-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda13-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bda13-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bda13-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bda13-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="bda13-107">in Der Exitcode für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="bda13-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bda13-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bda13-108">Return Value</span></span>  
 <span data-ttu-id="bda13-109">Diese Methode gibt nie zurück, sodass Ihr Rückgabewert nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="bda13-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bda13-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bda13-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bda13-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bda13-111">Requirements</span></span>  
 <span data-ttu-id="bda13-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bda13-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda13-113">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="bda13-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bda13-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bda13-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bda13-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda13-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda13-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bda13-116">See also</span></span>

- [<span data-ttu-id="bda13-117">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bda13-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="bda13-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="bda13-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
