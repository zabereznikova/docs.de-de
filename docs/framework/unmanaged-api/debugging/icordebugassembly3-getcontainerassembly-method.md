---
title: ICorDebugAssembly3::GetContainerAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c7bf800c75083fa81ab2bb14d4ad13f08050dc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly3getcontainerassembly-method"></a>ICorDebugAssembly3::GetContainerAssembly-Methode
Gibt die Container-Assembly dieses `ICorDebugAssembly3`-Objekts aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppAssembly`  
 Ein Zeiger auf die Adresse eines ICorDebugAssembly-Objekts, das die Container-Assembly darstellt oder **null** , wenn der Methodenaufruf fehlschlägt.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn der Methodenaufruf erfolgreich ist. andernfalls `S_FALSE`, und `ppAssembly` ist **null**.  
  
## <a name="remarks"></a>Hinweise  
 Wenn diese Assembly mit anderen Benutzern in einer einzelnen Container-Assembly zusammengeführt wurde, gibt diese Methode die Container-Assembly aus. Weitere Informationen und Terminologie finden Sie in der [icordebugprocess6:: Enablevirtualmodulesplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) Thema.  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugAssembly3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
