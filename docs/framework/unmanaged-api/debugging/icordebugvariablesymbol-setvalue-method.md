---
title: ICorDebugVariableSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
ms.openlocfilehash: 3ef9b9b9a095d6d6026ffc38873661355d660488
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707840"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a>ICorDebugVariableSymbol::GetSize-Methode

Weist einer Variablen den Wert eines Bytearrays zu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `offset`  
 [in] Der Startoffset in der Variablen, an dem der Wert festgelegt werden soll. Dieser Parameter wird verwendet, wenn in Memberfelder in einem Objekt geschrieben wird.  
  
 `threadID`  
 [in] Der Threadbezeichner des Threads, dessen Kontext aktualisiert werden muss, damit der neue Wert berücksichtigt wird.  
  
 `cbContext`  
 [in] Die Größe des Threadkontexts in Byte.  
  
 `context`  
 [in] Der Threadkontext, der zum Schreiben des Werts verwendet wird.  
  
 `cbValue`  
 [in] Die Größe des `pValue`-Puffers in Byte.  
  
 `pValue`  
 [in] Der Puffer, der den festzulegenden Wert enthält.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugVariableSymbol-Schnittstelle](icordebugvariablesymbol-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
