---
title: ICorDebugVirtualUnwinder::GetContext-Methode
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
ms.openlocfilehash: e203db78b40bf4305316046cfcd679f3d10d1876
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396435"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a>ICorDebugVirtualUnwinder::GetContext-Methode
Ruft den aktuellen Kontext dieses Entladers ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `contextFlags`  
 [in] Flags, die angeben, welche Teile des Kontexts zurückgegeben werden (in "WinNT.h" definiert).  
  
 `cbContextBuf`  
 [in] Die Anzahl von Bytes in `contextBuf`.  
  
 `contextSize`  
 [out] Ein Zeiger auf die Anzahl der tatsächlich in `contextBuf` geschriebenen Bytes.  
  
 `contextBuf`  
 [out] Ein Bytearray, das den aktuellen Kontext dieses Entladers enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Alle von "mscordbi" empfangenen HRESULT-Fehlerwerte gelten als schwerwiegend und bewirken, dass "ICorDebug"-APIs `CORDBG_E_DATA_TARGET_ERROR` zurückgeben.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie legen den Anfangswert des `contextBuf` Arguments auf den Kontext Puffer fest, der durch Aufrufen der [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) -Methode zurückgegeben wird.  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
 Da beim Entladen möglicherweise nur eine Teilmenge der Register (z. B. nur die nicht permanenten Register) wiederhergestellt werden, stimmt der Kontext möglicherweise nicht genau mit dem Registrierungszustand zum Zeitpunkt des eigentlichen Methodenaufrufs überein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugMemoryBuffer-Schnittstelle](icordebugmemorybuffer-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
