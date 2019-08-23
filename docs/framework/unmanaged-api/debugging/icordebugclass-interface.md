---
title: ICorDebugClass-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc5099af23a2b706694bfcb655d295607c97ea8a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969271"
---
# <a name="icordebugclass-interface"></a>ICorDebugClass-Schnittstelle

Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann. Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetModule-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Ruft das Modul ab, das diese Klasse definiert.|  
|[GetStaticFieldValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|Ruft den Wert des angegebenen statischen Felds ab.|  
|[GetToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|Ruft das `TypeDef` Metadatentoken für diese Klasse ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugClass` -Schnittstelle stellt einen nicht instanziierten generischen Typ dar. Die ICorDebugType-Schnittstelle stellt einen instanziierten generischen Typ dar. Beispielsweise `Hashtable<K, V>` wird durch `ICorDebugClass`dargestellt, wohingegen `Hashtable<Int32, String>` von `ICorDebugType`dargestellt wird.  
  
 Nicht generische Typen werden sowohl `ICorDebugClass` von als auch `ICorDebugType`von dargestellt. Die zweite Schnittstelle wurde in der .NET Framework Version 2,0 eingeführt, um die Typinstanziierung zu behandeln.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
