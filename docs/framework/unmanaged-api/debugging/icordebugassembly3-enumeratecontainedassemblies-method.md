---
title: ICorDebugAssembly3::EnumerateContainedAssemblies-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b927d065f26a13d496aec8cd6c8cbc69cf3a8bc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a>ICorDebugAssembly3::EnumerateContainedAssemblies-Methode
Ruft einen Enumerator für die Assemblys ab, die in dieser Assembly enthalten sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppAssemblies`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugAssemblyEnum-Schnittstelle-Objekts, das den Enumerator darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, falls dieses `ICorDebugAssembly3`-Objekt ein Container ist; andernfalls `S_FALSE`, und die Enumeration ist leer.  
  
## <a name="remarks"></a>Hinweise  
 Symbole sind erforderlich, um die darin enthaltenen Assemblys aufzuführen. Wenn sie nicht vorhanden sind, gibt die Methode `S_FALSE` aus, und es wird kein gültiger Enumerator bereitgestellt.  
  
> [!NOTE]
>  Diese Methode ist nur in Verbindung mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugAssembly3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
