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
ms.workload: dotnet
ms.openlocfilehash: a47eb051cd9922b8640b8b612ff0ac5882b6a8ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="0a109-102">ICorDebugMergedAssemblyRecord::GetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="0a109-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="0a109-103">Ruft den öffentlichen Schlüssel der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="0a109-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a109-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a109-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a109-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0a109-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="0a109-106">[in] Die maximale Anzahl der Bytes im `pbPublicKey`-Array.</span><span class="sxs-lookup"><span data-stu-id="0a109-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="0a109-107">[out] Ein Zeiger auf die tatsächliche Anzahl der in den `pbPublicKey`-Array geschriebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="0a109-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="0a109-108">[out] Ein Zeiger auf ein Bytearray, das den öffentlichen Schlüssel der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="0a109-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a109-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a109-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a109-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0a109-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a109-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0a109-111">Requirements</span></span>  
 <span data-ttu-id="0a109-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a109-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a109-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a109-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a109-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a109-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a109-115">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a109-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a109-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a109-116">See Also</span></span>  
 [<span data-ttu-id="0a109-117">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a109-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="0a109-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0a109-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
