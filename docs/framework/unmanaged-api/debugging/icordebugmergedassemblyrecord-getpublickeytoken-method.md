---
title: ICorDebugMergedAssemblyRecord::GetPublicKeyToken-Methode
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a4a8e5f99a845d2befe55f5939b41224f2aa47b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077302"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="1ef48-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="1ef48-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>
<span data-ttu-id="1ef48-103">Ruft das öffentliche Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="1ef48-103">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ef48-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ef48-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ef48-105">Parameters</span></span>  
 `cbPublicKeyToken`  
 <span data-ttu-id="1ef48-106">[in] Die maximale Anzahl der Bytes im `pbPublicKeyToken`-Array.</span><span class="sxs-lookup"><span data-stu-id="1ef48-106">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="1ef48-107">[out] Ein Zeiger auf die tatsächliche Anzahl der in den `pbPublicKeyToken`-Array geschriebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="1ef48-107">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="1ef48-108">[out] Ein Zeiger auf ein Bytearray, das das öffentliche Schlüsseltoken der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="1ef48-108">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ef48-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ef48-109">Remarks</span></span>  
 <span data-ttu-id="1ef48-110">Das öffentliche Schlüsseltoken einer Assembly sind die letzten acht Bytes des SHA1-Hash ihres öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="1ef48-110">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ef48-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1ef48-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ef48-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ef48-112">Requirements</span></span>  
 <span data-ttu-id="1ef48-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ef48-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ef48-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ef48-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ef48-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ef48-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1ef48-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1ef48-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1ef48-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ef48-117">See also</span></span>

- [<span data-ttu-id="1ef48-118">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ef48-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="1ef48-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1ef48-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
