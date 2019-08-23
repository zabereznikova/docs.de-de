---
title: 'Icordebugmergedassemblyrecord:: GetPublicKey-Methode'
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e08b1edcef3e93caa82be3a4342c6a0264734bea
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940022"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="f41eb-102">Icordebugmergedassemblyrecord:: GetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="f41eb-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="f41eb-103">Ruft den öffentlichen Schlüssel der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="f41eb-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f41eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f41eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f41eb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f41eb-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="f41eb-106">[in] Die maximale Anzahl der Bytes im `pbPublicKey`-Array.</span><span class="sxs-lookup"><span data-stu-id="f41eb-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="f41eb-107">[out] Ein Zeiger auf die tatsächliche Anzahl der in den `pbPublicKey`-Array geschriebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="f41eb-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="f41eb-108">[out] Ein Zeiger auf ein Bytearray, das den öffentlichen Schlüssel der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="f41eb-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f41eb-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f41eb-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f41eb-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f41eb-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f41eb-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f41eb-111">Requirements</span></span>  
 <span data-ttu-id="f41eb-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f41eb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f41eb-113">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f41eb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f41eb-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f41eb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f41eb-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f41eb-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f41eb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f41eb-116">See also</span></span>

- [<span data-ttu-id="f41eb-117">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f41eb-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="f41eb-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f41eb-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
