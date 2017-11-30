---
title: ICorDebugSymbolProvider::GetCodeRange-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c46fb62e5f1867e2b527404bd3d003ba884ebfbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="ac736-102">ICorDebugSymbolProvider::GetCodeRange-Methode</span><span class="sxs-lookup"><span data-stu-id="ac736-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="ac736-103">Ruft die Startadresse und Größe einer Methode ab, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ac736-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac736-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac736-104">Syntax</span></span>  
  
```  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac736-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac736-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="ac736-106">[in] Die relative virtuelle Adresse (RVA) in einer Methode.</span><span class="sxs-lookup"><span data-stu-id="ac736-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="ac736-107">[out] Ein Zeiger auf die Startadresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="ac736-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="ac736-108">Ein Zeiger auf die Größe des Codes der Methode (die Anzahl von Bytes des Codes der Methode).</span><span class="sxs-lookup"><span data-stu-id="ac736-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac736-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac736-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac736-110">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ac736-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac736-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac736-111">Requirements</span></span>  
 <span data-ttu-id="ac736-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac736-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac736-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac736-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac736-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac736-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac736-115">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac736-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac736-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac736-116">See Also</span></span>  
 [<span data-ttu-id="ac736-117">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac736-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="ac736-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ac736-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
