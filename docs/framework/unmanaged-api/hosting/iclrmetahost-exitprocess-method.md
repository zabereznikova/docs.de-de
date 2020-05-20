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
ms.openlocfilehash: 83cbfa097541681305ff285f21c2b6c9c6391ef8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703749"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="d92b3-102">ICLRMetaHost::ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="d92b3-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="d92b3-103">Versucht, alle geladenen Laufzeiten ordnungsgemäß herunterzufahren, und beendet dann den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="d92b3-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="d92b3-104">Ersetzt die [CorExitProcess](corexitprocess-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="d92b3-104">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d92b3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d92b3-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d92b3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d92b3-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="d92b3-107">in Der Exitcode für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="d92b3-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d92b3-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d92b3-108">Return Value</span></span>  
 <span data-ttu-id="d92b3-109">Diese Methode gibt nie zurück, sodass Ihr Rückgabewert nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d92b3-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d92b3-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d92b3-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d92b3-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d92b3-111">Requirements</span></span>  
 <span data-ttu-id="d92b3-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d92b3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d92b3-113">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="d92b3-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d92b3-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d92b3-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d92b3-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d92b3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d92b3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d92b3-116">See also</span></span>

- [<span data-ttu-id="d92b3-117">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d92b3-117">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="d92b3-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="d92b3-118">Hosting</span></span>](index.md)
