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
ms.openlocfilehash: 50ea9caf08b2ffb689760da95af4e5c3fdd77301
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793738"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="c6634-102">ICLRDataTarget::GetMachineType-Methode</span><span class="sxs-lookup"><span data-stu-id="c6634-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="c6634-103">Ruft den Bezeichner für die Art von Anweisungs Satz ab, die vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6634-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6634-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6634-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6634-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c6634-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="c6634-106">vorgenommen Ein Zeiger auf einen Wert, der den Anweisungs Satz angibt, der vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6634-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="c6634-107">Der zurückgegebene `machineType` ist eine der IMAGE_FILE_MACHINE Konstanten, die in der Header Datei "Winnt. h" definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c6634-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6634-108">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6634-108">Requirements</span></span>  
 <span data-ttu-id="c6634-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6634-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6634-110">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="c6634-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c6634-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6634-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6634-112">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6634-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6634-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6634-113">See also</span></span>

- [<span data-ttu-id="c6634-114">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6634-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
