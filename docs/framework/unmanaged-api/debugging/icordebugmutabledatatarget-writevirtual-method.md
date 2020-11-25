---
title: ICorDebugMutableDataTarget::WriteVirtual-Methode
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 453ab23e292c5eab4a8300c32bf76743b787750d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709335"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a>ICorDebugMutableDataTarget::WriteVirtual-Methode

Schreibt Speicher in den Prozessadressraum.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a>Parameter  

 `address`  
 [in] Die Adresse, an die der Inhalt von `pBuffer` geschrieben wird.  
  
 `pBuffer`  
 [in] Ein Zeiger auf ein Bytearray, das die zu schreibenden Bytes enthält.  
  
 `address`  
 [in] Die Anzahl von Bytes in `pBuffer`.  
  
## <a name="return-value"></a>Rückgabewert  

 `S_OK` bei erfolgreichem Verlauf oder ein anderes `HRESULT` im Fall eines Fehlers.  
  
## <a name="remarks"></a>Hinweise  

 Wenn Bytes nicht geschrieben werden können, tritt ein Fehler beim Methodenaufruf auf, und es werden keine Bytes im Zieladressraum geändert. (Andernfalls würde sich das Ziel in einem inkonsistenten Zustand befinden, wodurch ein weiteres Debuggen unzuverlässig wäre.)  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugMutableDataTarget-Schnittstelle](icordebugmutabledatatarget-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
