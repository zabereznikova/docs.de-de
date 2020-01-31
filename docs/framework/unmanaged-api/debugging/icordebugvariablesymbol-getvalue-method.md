---
title: ICorDebugVariableSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: 2dc074384d209d0740a1fb0a9a16d96ff355f02b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790883"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a>ICorDebugVariableSymbol::GetSize-Methode
Ruft den Wert einer Variablen als Bytearray ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `offset`  
 [in] Der Startoffset in der Variablen, aus der der Wert gelesen werden soll. Dieser Parameter wird beim Lesen von Memberfeldern in einem Objekt verwendet.  
  
 `cbContext`  
 [in] Die Größe des `context`-Arguments in Byte.  
  
 `context`  
 [in] Der zum Lesen des Werts verwendete Threadkontext.  
  
 `cbValue`  
 [in] Die Größe des `pValue`-Puffers in Byte.  
  
 `pcbValue`  
 [out] Die Anzahl der tatsächlich in den `pValue`-Puffer geschriebenen Bytes.  
  
 `pValue`  
 [out] Ein Bytearray, das den Wert der Variablen enthält.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugVariableSymbol-Schnittstelle](icordebugvariablesymbol-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
