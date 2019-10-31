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
ms.openlocfilehash: 941d1b4057ef78a6235a0ba853e48a000f2087e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122890"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="e0b4f-102">ICLRDataTarget::GetMachineType-Methode</span><span class="sxs-lookup"><span data-stu-id="e0b4f-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="e0b4f-103">Ruft den Bezeichner für die Art von Anweisungs Satz ab, die vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0b4f-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0b4f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0b4f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0b4f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0b4f-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="e0b4f-106">vorgenommen Ein Zeiger auf einen Wert, der den Anweisungs Satz angibt, der vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0b4f-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="e0b4f-107">Der zurückgegebene `machineType` ist eine der IMAGE_FILE_MACHINE-Konstanten, die in der Header Datei "Winnt. h" definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e0b4f-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0b4f-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0b4f-108">Requirements</span></span>  
 <span data-ttu-id="e0b4f-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0b4f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0b4f-110">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="e0b4f-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e0b4f-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0b4f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0b4f-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0b4f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0b4f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0b4f-113">See also</span></span>

- [<span data-ttu-id="e0b4f-114">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0b4f-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
