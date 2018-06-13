---
title: ICLRDataTarget::GetMachineType-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c515a8184e8c01b0e292057f3f66ffef28f2c5fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402880"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="80100-102">ICLRDataTarget::GetMachineType-Methode</span><span class="sxs-lookup"><span data-stu-id="80100-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="80100-103">Ruft den Bezeichner für die Art der Anweisungssatz, der der Zielprozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="80100-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80100-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80100-104">Syntax</span></span>  
  
```  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80100-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="80100-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="80100-106">[out] Ein Zeiger auf einen Wert, der angibt, dass die Anweisung, die den Zielprozess festgelegt wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="80100-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="80100-107">Das zurückgegebene `machineType` ist einer der IMAGE_FILE_MACHINE-Konstanten, die in der Headerdatei "Winnt.h" definiert sind.</span><span class="sxs-lookup"><span data-stu-id="80100-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80100-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80100-108">Requirements</span></span>  
 <span data-ttu-id="80100-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80100-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80100-110">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="80100-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="80100-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80100-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80100-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80100-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80100-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80100-113">See Also</span></span>  
 [<span data-ttu-id="80100-114">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80100-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
