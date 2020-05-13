---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata-Methode
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: d118f0c984663e0844783ff52859698dd5335058
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376143"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a>ICorDebugSymbolProvider::GetAssemblyImageMetadata-Methode
Gibt die Metadaten aus einer zusammengeführten Assembly zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppMemoryBuffer`  
 vorgenommen Ein Zeiger auf die Adresse eines [icordebugmemorybuffer](icordebugmemorybuffer-interface.md) -Objekts, das Informationen über die Größe und die Adresse der Metadaten der zusammengeführten Assembly enthält.  
  
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
