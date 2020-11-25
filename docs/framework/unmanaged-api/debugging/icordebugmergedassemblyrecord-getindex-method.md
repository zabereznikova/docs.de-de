---
title: ICorDebugMergedAssemblyRecord::GetIndex-Methode
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: 3056d22f5ddc1b11b79ee072aba68ce3ad40e8da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710635"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a>ICorDebugMergedAssemblyRecord::GetIndex-Methode

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
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugMergedAssemblyRecord-Schnittstelle](icordebugmergedassemblyrecord-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
