---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes-Methode
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: b52614065d599edf8e556524c33e8bc50b4924ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709179"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a>ICorDebugSymbolProvider::GetAssemblyImageBytes-Methode

Liest Daten aus einer zusammengeführten Assembly, wenn eine relative virtuelle Adresse (RVA) in der zusammengeführten Assembly angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 Ein Zeiger auf die Adresse eines [icordebugmemorybuffer](icordebugmemorybuffer-interface.md) -Objekts, das Informationen über den Arbeitsspeicher Puffer mit zusammengeführten Assemblymetadaten enthält.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugSymbolProvider-Schnittstelle](icordebugsymbolprovider-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
