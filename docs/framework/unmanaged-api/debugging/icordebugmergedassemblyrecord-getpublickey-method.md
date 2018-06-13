---
title: ICorDebugMergedAssemblyRecord::GetPublicKey-Methode
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 743772b3578cdbd92f66a58d2599a97c896e8172
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413734"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="a28d7-102">ICorDebugMergedAssemblyRecord::GetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="a28d7-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="a28d7-103">Ruft den öffentlichen Schlüssel der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="a28d7-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a28d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a28d7-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a28d7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a28d7-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="a28d7-106">[in] Die maximale Anzahl der Bytes im `pbPublicKey`-Array.</span><span class="sxs-lookup"><span data-stu-id="a28d7-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="a28d7-107">[out] Ein Zeiger auf die tatsächliche Anzahl der in den `pbPublicKey`-Array geschriebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="a28d7-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="a28d7-108">[out] Ein Zeiger auf ein Bytearray, das den öffentlichen Schlüssel der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="a28d7-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a28d7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a28d7-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a28d7-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a28d7-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a28d7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a28d7-111">Requirements</span></span>  
 <span data-ttu-id="a28d7-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a28d7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a28d7-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a28d7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a28d7-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a28d7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a28d7-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a28d7-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a28d7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a28d7-116">See Also</span></span>  
 [<span data-ttu-id="a28d7-117">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a28d7-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="a28d7-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a28d7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
