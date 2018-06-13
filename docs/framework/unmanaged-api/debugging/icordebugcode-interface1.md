---
title: ICorDebugCode Schnittstelle1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37917577c802514fcebc3ea0792cbce9bb8a7345
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414078"
---
# <a name="icordebugcode-interface1"></a>ICorDebugCode Schnittstelle1
Stellt ein Segment von Microsoft Intermediate Language (MSIL)-Code oder nativem Code dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|Erstellt am angegebenen Offset einen Haltepunkt.|  
|[GetAddress-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|Ruft die relative virtuelle Adresse (RVA) des Codesegments ab, das diesen `ICorDebugCode` darstellt.|  
|[GetCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab. Diese Methode wurde als veraltet markiert; Verwenden Sie [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) stattdessen.|  
|[GetEnCRemapSequencePoints-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|Nicht implementiert.|  
|[GetFunction-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|Ruft "ICorDebugFunction" zugeordnete `ICorDebugCode`.|  
|[GetILToNativeMapping-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|Ruft ein Array von "COR_DEBUG_IL_TO_NATIVE_MAP"-Instanzen, die Zuordnungen zwischen MSIL-Offsets und systemeigenen Offsets darstellen.|  
|[GetSize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|Ruft die Größe des Binärcodes in Bytes ab, der durch diesen `ICorDebugCode` dargestellt wird.|  
|[GetVersionNumber-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|Ruft die mit eins beginnende Zahl ab, die die Version des Codes angibt, den dieser `ICorDebugCode` darstellt.|  
|[IsIL-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|Ruft einen Wert ab, der angibt, ob dieser `ICorDebugCode` in MSIL kompiliert wird.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugCode` kann entweder MSIL- oder systemeigenen Code darstellen. Ein "ICorDebugFunction"-Objekt, das MSIL-Code darstellt können NULL oder eins `ICorDebugCode` -Objekten zugeordnet sein. Ein "ICorDebugFunction"-Objekt, das systemeigenen Code darstellt, kann eine beliebige Anzahl von haben `ICorDebugCode` -Objekten zugeordnet sein.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
    
 [ICorDebugCode3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
