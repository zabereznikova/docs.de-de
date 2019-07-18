---
title: ICorDebugAssembly3::EnumerateContainedAssemblies-Methode
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05c4e2a5c16f11f80cc8356a65b746eab81a3899
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744399"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a>ICorDebugAssembly3::EnumerateContainedAssemblies-Methode
Ruft einen Enumerator für die Assemblys ab, die in dieser Assembly enthalten sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppAssemblies`  
 [out] Ein Zeiger auf die Adresse der Schnittstelle ICorDebugAssemblyEnum-Objekts, das den Enumerator darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, falls dieses `ICorDebugAssembly3`-Objekt ein Container ist; andernfalls `S_FALSE`, und die Enumeration ist leer.  
  
## <a name="remarks"></a>Hinweise  
 Symbole sind erforderlich, um die darin enthaltenen Assemblys aufzuführen. Wenn sie nicht vorhanden sind, gibt die Methode `S_FALSE` aus, und es wird kein gültiger Enumerator bereitgestellt.  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugAssembly3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
