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
ms.openlocfilehash: 00601e0bc722c0dc5e972324eddc0ab073d04586
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703537"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="5ff2b-102">ICLRDataTarget::GetMachineType-Methode</span><span class="sxs-lookup"><span data-stu-id="5ff2b-102">ICLRDataTarget::GetMachineType Method</span></span>

<span data-ttu-id="5ff2b-103">Ruft den Bezeichner für die Art von Anweisungs Satz ab, die vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff2b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ff2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ff2b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ff2b-105">Parameters</span></span>  

 `machineType`  
 <span data-ttu-id="5ff2b-106">vorgenommen Ein Zeiger auf einen Wert, der den Anweisungs Satz angibt, der vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="5ff2b-107">Der zurückgegebene `machineType` ist eine der IMAGE_FILE_MACHINE Konstanten, die in der Header Datei "Winnt. h" definiert sind.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff2b-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5ff2b-108">Requirements</span></span>  

 <span data-ttu-id="5ff2b-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ff2b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ff2b-110">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="5ff2b-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5ff2b-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ff2b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ff2b-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ff2b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff2b-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ff2b-113">See also</span></span>

- [<span data-ttu-id="5ff2b-114">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ff2b-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
