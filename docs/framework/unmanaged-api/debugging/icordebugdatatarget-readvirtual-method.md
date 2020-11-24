---
title: ICorDebugDataTarget::ReadVirtual-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
ms.openlocfilehash: 8fb0cfc72867653eaff65f3183dacf9191604290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679727"
---
# <a name="icordebugdatatargetreadvirtual-method"></a>ICorDebugDataTarget::ReadVirtual-Methode

Ruft einen Block von zusammenhängenden Arbeitsspeicher ab, der bei der angegebenen Adresse beginnt, und gibt ihn im angegebenen Puffer zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a>Parameter  

 `address`  
 in Die Startadresse des angeforderten Speichers.  
  
 `pbuffer`  
 vorgenommen Der Puffer, in dem der Arbeitsspeicher gespeichert wird.  
  
 `bytesRequested`  
 in Die Anzahl der Bytes, die von der Zieladresse abgeleitet werden sollen.  
  
 `pBytesRead`  
 vorgenommen Die Anzahl der tatsächlich von der Zieladresse gelesenen Bytes. Dies kann weniger als sein `bytesRequested` .  
  
## <a name="remarks"></a>Hinweise  

 Wenn das erste Byte (an der angegebenen Startadresse) gelesen werden kann, sollte der-Befehl einen Erfolg zurückgeben (um das effiziente Lesen von Datenstrukturen mit selbst beschreibender Länge zu unterstützen, wie z. b. auf NULL endende Zeichen folgen).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugDataTarget-Schnittstelle](icordebugdatatarget-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
