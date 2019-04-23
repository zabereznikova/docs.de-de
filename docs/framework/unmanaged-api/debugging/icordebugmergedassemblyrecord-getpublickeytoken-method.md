---
title: ICorDebugMergedAssemblyRecord::GetPublicKeyToken-Methode
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a4a8e5f99a845d2befe55f5939b41224f2aa47b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077302"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="c00f6-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="c00f6-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>
<span data-ttu-id="c00f6-103">Ruft das öffentliche Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="c00f6-103">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c00f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c00f6-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c00f6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c00f6-105">Parameters</span></span>  
 `cbPublicKeyToken`  
 <span data-ttu-id="c00f6-106">[in] Die maximale Anzahl der Bytes im `pbPublicKeyToken`-Array.</span><span class="sxs-lookup"><span data-stu-id="c00f6-106">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="c00f6-107">[out] Ein Zeiger auf die tatsächliche Anzahl der in den `pbPublicKeyToken`-Array geschriebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="c00f6-107">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="c00f6-108">[out] Ein Zeiger auf ein Bytearray, das das öffentliche Schlüsseltoken der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="c00f6-108">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c00f6-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c00f6-109">Remarks</span></span>  
 <span data-ttu-id="c00f6-110">Das öffentliche Schlüsseltoken einer Assembly sind die letzten acht Bytes des SHA1-Hash ihres öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="c00f6-110">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c00f6-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c00f6-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c00f6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c00f6-112">Requirements</span></span>  
 <span data-ttu-id="c00f6-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c00f6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c00f6-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c00f6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c00f6-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c00f6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c00f6-116">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c00f6-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00f6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c00f6-117">See also</span></span>

- [<span data-ttu-id="c00f6-118">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c00f6-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="c00f6-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c00f6-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
