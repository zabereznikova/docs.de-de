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
ms.openlocfilehash: f0188facf0b7d33e6e1ecc12921a139165f777a1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686630"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="35aac-102">CreateCoreClrDebugTarget-Funktion</span><span class="sxs-lookup"><span data-stu-id="35aac-102">CreateCoreClrDebugTarget Function</span></span>

<span data-ttu-id="35aac-103">Erstellt eine Verbindung mit einem debuggerproxy, der auf einem Remote Computer ausgeführt wird, und gibt ein [icoreclrdebugtarget](icoreclrdebugtarget-interface.md) -Objekt zurück, das zum Abfragen von laufenden Prozessen und geladenen Laufzeiten auf dem Remote Computer verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="35aac-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35aac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35aac-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35aac-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="35aac-105">Parameters</span></span>  

 `dwAddress`  
 <span data-ttu-id="35aac-106">[in] IPv4-Adresse eines Remotezielcomputers.</span><span class="sxs-lookup"><span data-stu-id="35aac-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="35aac-107">vorgenommen Zeiger auf einen Zeiger auf ein [icoreclrdebugtarget](icoreclrdebugtarget-interface.md) -Objekt, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="35aac-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35aac-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="35aac-108">Return Value</span></span>  

 <span data-ttu-id="35aac-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="35aac-109">S_OK</span></span>  
 <span data-ttu-id="35aac-110">Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="35aac-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="35aac-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="35aac-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="35aac-112">Für `ppTarget` kann nicht genug Arbeitsspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="35aac-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="35aac-113">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="35aac-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="35aac-114">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="35aac-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35aac-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="35aac-115">Requirements</span></span>  

 <span data-ttu-id="35aac-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35aac-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35aac-117">**Header:** Coreclrremotedebugginginterfaces. h</span><span class="sxs-lookup"><span data-stu-id="35aac-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="35aac-118">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="35aac-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="35aac-119">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="35aac-119">**.NET Framework Versions:** 3.5 SP1</span></span>
