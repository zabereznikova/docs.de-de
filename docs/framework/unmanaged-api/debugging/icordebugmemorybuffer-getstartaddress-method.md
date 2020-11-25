---
title: ICorDebugMemoryBuffer::GetStartAddress-Methode
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f76bf1479db987e4956d8b876f67d629d927f956
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710757"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a>ICorDebugMemoryBuffer::GetStartAddress-Methode

Ruft die Startadresse des Speicherpuffers ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `address`  
 [out] Ein Zeiger auf die Startadresse des Speicherpuffers.  
  
## <a name="remarks"></a>Hinweise  
  
> [!WARNING]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugMemoryBuffer-Schnittstelle](icordebugmemorybuffer-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
