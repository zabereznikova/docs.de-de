---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes-Methode
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: a555acb9e23098b0a0f70924032771b1ae18e88e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376116"
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
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugSymbolProvider-Schnittstelle](icordebugsymbolprovider-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
