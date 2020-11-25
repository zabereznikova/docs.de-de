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
ms.openlocfilehash: 6d601ac3ece801353b630c74ed852c2657f25d7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730462"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="83853-102">ICLRMetaHost::ExitProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="83853-102">ICLRMetaHost::ExitProcess Method</span></span>

<span data-ttu-id="83853-103">Versucht, alle geladenen Laufzeiten ordnungsgemäß herunterzufahren, und beendet dann den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="83853-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="83853-104">Ersetzt die [CorExitProcess](corexitprocess-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="83853-104">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83853-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="83853-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83853-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="83853-106">Parameters</span></span>  

 `iExitCode`  
 <span data-ttu-id="83853-107">in Der Exitcode für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="83853-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83853-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="83853-108">Return Value</span></span>  

 <span data-ttu-id="83853-109">Diese Methode gibt nie zurück, sodass Ihr Rückgabewert nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="83853-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83853-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="83853-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83853-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="83853-111">Requirements</span></span>  

 <span data-ttu-id="83853-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83853-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83853-113">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="83853-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="83853-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="83853-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83853-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83853-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83853-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="83853-116">See also</span></span>

- [<span data-ttu-id="83853-117">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83853-117">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="83853-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="83853-118">Hosting</span></span>](index.md)
