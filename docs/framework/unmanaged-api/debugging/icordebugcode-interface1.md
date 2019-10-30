---
title: ICorDebugCode-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
ms.openlocfilehash: 8cb95fad4394e2ce9b7f922e720071d8c4434edb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125593"
---
# <a name="icordebugcode-interface"></a>ICorDebugCode-Schnittstelle

Stellt ein Segment von Microsoft Intermediate Language (MSIL)-Code oder nativem Code dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|Erstellt am angegebenen Offset einen Haltepunkt.|  
|[GetAddress-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|Ruft die relative virtuelle Adresse (RVA) des Codesegments ab, das diesen `ICorDebugCode` darstellt.|  
|[GetCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab. Diese Methode ist veraltet. Verwenden Sie stattdessen [ICorDebugCode2:: getcodechunert](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) .|  
|[GetEnCRemapSequencePoints-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|Nicht implementiert.|  
|[GetFunction-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|Ruft den "ICorDebug Function" ab, der diesem `ICorDebugCode`zugeordnet ist.|  
|[GetILToNativeMapping-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|Ruft ein Array von "COR_DEBUG_IL_TO_NATIVE_MAP"-Instanzen ab, die Zuordnungen von MSIL-Offsets zu systemeigenen Offsets darstellen.|  
|[GetSize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|Ruft die Größe des Binärcodes in Bytes ab, der durch diesen `ICorDebugCode` dargestellt wird.|  
|[GetVersionNumber-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|Ruft die mit eins beginnende Zahl ab, die die Version des Codes angibt, den dieser `ICorDebugCode` darstellt.|  
|[IsIL-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|Ruft einen Wert ab, der angibt, ob dieser `ICorDebugCode` in MSIL kompiliert wird.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugCode` kann entweder MSIL- oder systemeigenen Code darstellen. Ein ICorDebugFunction-Objekt, das MSIL-Code darstellt, kann entweder 0 (null) oder einen `ICorDebugCode` zugeordneten Objekten aufweisen. Einem ICorDebugFunction-Objekt, das systemeigenen Code darstellt, kann eine beliebige Anzahl von `ICorDebugCode`-Objekten zugeordnet sein.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugCode3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
