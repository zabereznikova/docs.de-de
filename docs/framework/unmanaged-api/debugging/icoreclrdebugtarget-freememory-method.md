---
title: ICoreClrDebugTarget::FreeMemory-Methode
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
ms.openlocfilehash: 1e159cacd297d56d63e512643ec4d3fe0c3709c0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694400"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="7e0fa-102">ICoreClrDebugTarget::FreeMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="7e0fa-102">ICoreClrDebugTarget::FreeMemory Method</span></span>

<span data-ttu-id="7e0fa-103">Gibt den von der [icoreclrdebugtarget:: EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) -Methode und der [icoreclrdebugtarget:: enumruntimes](icoreclrdebugtarget-enumruntimes-method.md) -Methode zugeordneten Arbeitsspeicher frei.</span><span class="sxs-lookup"><span data-stu-id="7e0fa-103">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e0fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e0fa-104">Syntax</span></span>  
  
```cpp  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e0fa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7e0fa-105">Parameters</span></span>  

 `pMemory`  
 <span data-ttu-id="7e0fa-106">in Ein Zeiger auf das Array, das entweder von der [icoreclrdebugtarget:: EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) -Methode oder der [icoreclrdebugtarget:: enumruntimes](icoreclrdebugtarget-enumruntimes-method.md) -Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7e0fa-106">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e0fa-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7e0fa-107">Requirements</span></span>  

 <span data-ttu-id="7e0fa-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e0fa-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e0fa-109">**Header:** Coreclrremotedebugginginterfaces. h</span><span class="sxs-lookup"><span data-stu-id="7e0fa-109">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="7e0fa-110">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="7e0fa-110">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="7e0fa-111">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="7e0fa-111">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e0fa-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e0fa-112">See also</span></span>

- [<span data-ttu-id="7e0fa-113">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e0fa-113">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
