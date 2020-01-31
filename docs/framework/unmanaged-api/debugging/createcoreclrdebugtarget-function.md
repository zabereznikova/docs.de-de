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
ms.openlocfilehash: a7fed8cb70785f0ccfcadf1e16181db303ac98e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789196"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="f558b-102">CreateCoreClrDebugTarget-Funktion</span><span class="sxs-lookup"><span data-stu-id="f558b-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="f558b-103">Erstellt eine Verbindung mit einem debuggerproxy, der auf einem Remote Computer ausgeführt wird, und gibt ein [icoreclrdebugtarget](icoreclrdebugtarget-interface.md) -Objekt zurück, das zum Abfragen von laufenden Prozessen und geladenen Laufzeiten auf dem Remote Computer verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f558b-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f558b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f558b-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f558b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f558b-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="f558b-106">[in] IPv4-Adresse eines Remotezielcomputers.</span><span class="sxs-lookup"><span data-stu-id="f558b-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="f558b-107">vorgenommen Zeiger auf einen Zeiger auf ein [icoreclrdebugtarget](icoreclrdebugtarget-interface.md) -Objekt, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f558b-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f558b-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f558b-108">Return Value</span></span>  
 <span data-ttu-id="f558b-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="f558b-109">S_OK</span></span>  
 <span data-ttu-id="f558b-110">Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="f558b-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="f558b-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f558b-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="f558b-112">Für `ppTarget` kann nicht genug Arbeitsspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f558b-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="f558b-113">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="f558b-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="f558b-114">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="f558b-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f558b-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f558b-115">Requirements</span></span>  
 <span data-ttu-id="f558b-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f558b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f558b-117">**Header:** Coreclrremotedebugginginterfaces. h</span><span class="sxs-lookup"><span data-stu-id="f558b-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="f558b-118">**Bibliothek:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="f558b-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="f558b-119">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="f558b-119">**.NET Framework Versions:** 3.5 SP1</span></span>
