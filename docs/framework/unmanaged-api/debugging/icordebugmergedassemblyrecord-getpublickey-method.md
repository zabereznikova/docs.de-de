---
title: ICorDebugMergedAssemblyRecord::GetPublicKey-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d379f0df70690501920a9ba5b40d560b10a7cb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="c274d-102">ICorDebugMergedAssemblyRecord::GetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="c274d-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="c274d-103">Ruft den öffentlichen Schlüssel der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="c274d-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c274d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c274d-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c274d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c274d-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="c274d-106">[in] Die maximale Anzahl der Bytes im `pbPublicKey`-Array.</span><span class="sxs-lookup"><span data-stu-id="c274d-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="c274d-107">[out] Ein Zeiger auf die tatsächliche Anzahl der in den `pbPublicKey`-Array geschriebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="c274d-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="c274d-108">[out] Ein Zeiger auf ein Bytearray, das den öffentlichen Schlüssel der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="c274d-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c274d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c274d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c274d-110">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c274d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c274d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c274d-111">Requirements</span></span>  
 <span data-ttu-id="c274d-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c274d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c274d-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c274d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c274d-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c274d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c274d-115">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c274d-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c274d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c274d-116">See Also</span></span>  
 [<span data-ttu-id="c274d-117">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c274d-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="c274d-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c274d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
