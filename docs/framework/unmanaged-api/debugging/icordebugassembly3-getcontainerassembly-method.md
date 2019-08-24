---
title: ICorDebugAssembly3::GetContainerAssembly-Methode
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4cda67145a0e624f87e93cf02ebdb6bc77c34d2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69987597"
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
 `S_OK`, wenn der Methoden Aufrufvorgang erfolgreich ist. Andernfalls ist `ppAssembly`,und **NULL.** `S_FALSE`  
  
## <a name="remarks"></a>Hinweise  
 Wenn diese Assembly mit anderen Benutzern in einer einzelnen Container-Assembly zusammengeführt wurde, gibt diese Methode die Container-Assembly aus. Weitere Informationen und die Terminologie finden Sie im Thema [ICorDebugProcess6:: enablevirtualmodulesplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) .  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugAssembly3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
