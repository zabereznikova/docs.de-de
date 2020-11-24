---
title: ICorDebugAssembly3::GetContainerAssembly-Methode
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 51e68e73983425cdd7d648b6856809fcba590f70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688548"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a>ICorDebugAssembly3::GetContainerAssembly-Methode

Gibt die Container-Assembly dieses `ICorDebugAssembly3`-Objekts aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppAssembly`  
 Ein Zeiger auf die Adresse eines ICorDebugAssembly-Objekts, das die containerassembly darstellt, oder **null** , wenn der Methodenaufrufe fehlschlägt.  
  
## <a name="return-value"></a>Rückgabewert  

 `S_OK` , wenn der Methoden Aufrufvorgang erfolgreich ist. andernfalls `S_FALSE` ist, und `ppAssembly` **null**.  
  
## <a name="remarks"></a>Hinweise  

 Wenn diese Assembly mit anderen Benutzern in einer einzelnen Container-Assembly zusammengeführt wurde, gibt diese Methode die Container-Assembly aus. Weitere Informationen und die Terminologie finden Sie im Thema [ICorDebugProcess6:: enablevirtualmodulesplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugAssembly3-Schnittstelle](icordebugassembly3-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
