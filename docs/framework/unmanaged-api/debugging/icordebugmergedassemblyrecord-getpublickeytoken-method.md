---
title: ICorDebugMergedAssemblyRecord::GetPublicKeyToken-Methode
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
ms.openlocfilehash: c642d8af7e84288d3aa8912372a2f169b8f22503
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710570"
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
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugMergedAssemblyRecord-Schnittstelle](icordebugmergedassemblyrecord-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
