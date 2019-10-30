---
title: 'Icordebugmergedassemblyrecord:: getIndex-Methode'
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: 236bd8b22d6c3ec783d787f6c906ede3193cfc1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131407"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a>Icordebugmergedassemblyrecord:: getIndex-Methode
Ruft den Präfixindex der Assembly ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pIndex`  
 [out] Ein Zeiger auf den Präfixindex.  
  
## <a name="remarks"></a>Hinweise  
 Der Präfixindex wird verwendet, um Namenskonflikte in den zusammengeführten Namen der Metadatentypen zu verhindern.  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugMergedAssemblyRecord-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
