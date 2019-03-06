---
title: CreateCoreClrDebugTarget-Funktion
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48ce5381c745669b813f5b28d801add7daba7825
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470064"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="7b480-102">CreateCoreClrDebugTarget-Funktion</span><span class="sxs-lookup"><span data-stu-id="7b480-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="7b480-103">Erstellt eine Verbindung mit einem Debuggerproxy, die auf einem Remotecomputer ausgeführt wird, und gibt eine [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) -Objekt, das zum Abfragen der ausgeführten Prozesse und geladene Laufzeitmodule auf dem Remotecomputer verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7b480-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b480-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b480-104">Syntax</span></span>  
  
```  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b480-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b480-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="7b480-106">[in] IPv4-Adresse eines Remotezielcomputers.</span><span class="sxs-lookup"><span data-stu-id="7b480-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="7b480-107">[out] Zeiger auf einen Zeiger auf ein [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) -Objekt, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7b480-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b480-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7b480-108">Return Value</span></span>  
 <span data-ttu-id="7b480-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b480-109">S_OK</span></span>  
 <span data-ttu-id="7b480-110">Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7b480-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="7b480-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7b480-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="7b480-112">Für `ppTarget` kann nicht genug Arbeitsspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7b480-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="7b480-113">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="7b480-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="7b480-114">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="7b480-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b480-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b480-115">Requirements</span></span>  
 <span data-ttu-id="7b480-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b480-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b480-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="7b480-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="7b480-118">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="7b480-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="7b480-119">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="7b480-119">**.NET Framework Versions:** 3.5 SP1</span></span>
