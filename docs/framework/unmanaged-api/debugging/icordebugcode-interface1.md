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
ms.openlocfilehash: 03cbc1a598ba6c0166f72ff404c239763956c996
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687605"
---
# <a name="icordebugcode-interface"></a>ICorDebugCode-Schnittstelle

Stellt ein Segment von Microsoft Intermediate Language (MSIL)-Code oder nativem Code dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](icordebugcode-createbreakpoint-method.md)|Erstellt am angegebenen Offset einen Haltepunkt.|  
|[GetAddress-Methode](icordebugcode-getaddress-method.md)|Ruft die relative virtuelle Adresse (RVA) des Codesegments ab, das diesen `ICorDebugCode` darstellt.|  
|[GetCode-Methode](icordebugcode-getcode-method.md)|Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab. Diese Methode ist veraltet. Verwenden Sie stattdessen [ICorDebugCode2:: getcodechunert](icordebugcode2-getcodechunks-method.md) .|  
|[GetEnCRemapSequencePoints-Methode](icordebugcode-getencremapsequencepoints-method.md)|Nicht implementiert.|  
|[GetFunction-Methode](icordebugcode-getfunction-method.md)|Ruft den "ICorDebug Function" ab, der diesem zugeordnet ist `ICorDebugCode` .|  
|[GetILToNativeMapping-Methode](icordebugcode-getiltonativemapping-method.md)|Ruft ein Array von "COR_DEBUG_IL_TO_NATIVE_MAP"-Instanzen ab, die Zuordnungen von MSIL-Offsets zu systemeigenen Offsets darstellen.|  
|[GetSize-Methode](icordebugcode-getsize-method.md)|Ruft die Größe des Binärcodes in Bytes ab, der durch diesen `ICorDebugCode` dargestellt wird.|  
|[GetVersionNumber-Methode](icordebugcode-getversionnumber-method.md)|Ruft die mit eins beginnende Zahl ab, die die Version des Codes angibt, den dieser `ICorDebugCode` darstellt.|  
|[IsIL-Methode](icordebugcode-isil-method.md)|Ruft einen Wert ab, der angibt, ob dieser `ICorDebugCode` in MSIL kompiliert wird.|  
  
## <a name="remarks"></a>Hinweise  

 `ICorDebugCode` kann entweder MSIL- oder systemeigenen Code darstellen. Einem ICorDebugFunction-Objekt, das MSIL-Code darstellt, kann entweder NULL oder ein-Objekt `ICorDebugCode` zugeordnet werden. Einem ICorDebugFunction-Objekt, das nativen Code darstellt, kann eine beliebige Anzahl von `ICorDebugCode` Objekten zugeordnet sein.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugCode3-Schnittstelle](icordebugcode3-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
