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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc71762fb4a660cf84814cdd46d09696a161f3c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431596"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="cccff-102">ICLRMetaHost::ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="cccff-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="cccff-103">Versucht, alle geladenen Laufzeiten ordnungsgemäß herunterzufahren, und klicken Sie dann beendet den Prozess.</span><span class="sxs-lookup"><span data-stu-id="cccff-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="cccff-104">Hat Vorrang vor den [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="cccff-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cccff-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cccff-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cccff-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="cccff-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="cccff-107">[in] Der Exitcode für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="cccff-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cccff-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cccff-108">Return Value</span></span>  
 <span data-ttu-id="cccff-109">Diese Methode gibt nie zurück, damit dessen Rückgabewert nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="cccff-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cccff-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cccff-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cccff-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cccff-111">Requirements</span></span>  
 <span data-ttu-id="cccff-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cccff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cccff-113">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="cccff-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cccff-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cccff-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cccff-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cccff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cccff-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cccff-116">See Also</span></span>  
 [<span data-ttu-id="cccff-117">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cccff-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="cccff-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="cccff-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
