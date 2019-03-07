---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes-Methode
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c44260d3b5baa18bc24f85cdbea94016b43291e2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489784"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a>ICorDebugSymbolProvider::GetAssemblyImageBytes-Methode
Liest Daten aus einer zusammengeführten Assembly, wenn eine relative virtuelle Adresse (RVA) in der zusammengeführten Assembly angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `rva`  
 [in] Eine relative virtuelle Adresse (RVA) in einer zusammengeführten Assembly.  
  
 `length`  
 Die Anzahl der Bytes, die aus der zusammengeführten Assembly gelesen. werden sollen.  
  
 `ppMemoryBuffer`  
 Ein Zeiger auf die Adresse einer [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) -Objekt, das Informationen zu dem Speicherpuffer mit Metadaten der zusammengeführten Assembly enthält.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugSymbolProvider-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
