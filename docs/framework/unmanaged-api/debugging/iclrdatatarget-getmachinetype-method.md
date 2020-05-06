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
ms.openlocfilehash: 9d86b23b91702929a86334f557a8d647e19861a4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860592"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="daea8-102">ICLRDataTarget::GetMachineType-Methode</span><span class="sxs-lookup"><span data-stu-id="daea8-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="daea8-103">Ruft den Bezeichner für die Art von Anweisungs Satz ab, die vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="daea8-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daea8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="daea8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daea8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="daea8-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="daea8-106">vorgenommen Ein Zeiger auf einen Wert, der den Anweisungs Satz angibt, der vom Ziel Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="daea8-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="daea8-107">Der zurück `machineType` gegebene ist eine der IMAGE_FILE_MACHINE Konstanten, die in der Header Datei "Winnt. h" definiert sind.</span><span class="sxs-lookup"><span data-stu-id="daea8-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daea8-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="daea8-108">Requirements</span></span>  
 <span data-ttu-id="daea8-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daea8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daea8-110">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="daea8-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="daea8-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daea8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daea8-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daea8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daea8-113">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="daea8-113">See also</span></span>

- [<span data-ttu-id="daea8-114">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="daea8-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
