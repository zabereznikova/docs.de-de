---
title: ICorDebugMergedAssemblyRecord::GetPublicKeyToken-Methode
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cc02c1f69235403e2f5df28168e17a70f183682
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762411"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a>ICorDebugMergedAssemblyRecord::GetPublicKeyToken-Methode
Ruft das öffentliche Schlüsseltoken der Assembly ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cbPublicKeyToken`  
 [in] Die maximale Anzahl der Bytes im `pbPublicKeyToken`-Array.  
  
 `pcbPublicKeyToken`  
 [out] Ein Zeiger auf die tatsächliche Anzahl der in den `pbPublicKeyToken`-Array geschriebenen Bytes.  
  
 `pbPublicKeyToken`  
 [out] Ein Zeiger auf ein Bytearray, das das öffentliche Schlüsseltoken der Assembly enthält.  
  
## <a name="remarks"></a>Hinweise  
 Das öffentliche Schlüsseltoken einer Assembly sind die letzten acht Bytes des SHA1-Hash ihres öffentlichen Schlüssels.  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugMergedAssemblyRecord-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
