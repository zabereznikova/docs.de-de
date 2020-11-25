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
ms.openlocfilehash: 4f488741f4233f06c128e0a262ce798ef27af3ff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699637"
---
# <a name="icordebugclass-interface"></a>ICorDebugClass-Schnittstelle

Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann. Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetModule-Methode](icordebugclass-getmodule-method.md)|Ruft das Modul ab, das diese Klasse definiert.|  
|[GetStaticFieldValue-Methode](icordebugclass-getstaticfieldvalue-method.md)|Ruft den Wert des angegebenen statischen Felds ab.|  
|[GetToken-Methode](icordebugclass-gettoken-method.md)|Ruft das `TypeDef` Metadatentoken für diese Klasse ab.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `ICorDebugClass` Schnittstelle stellt einen nicht instanziierten generischen Typ dar. Die ICorDebugType-Schnittstelle stellt einen instanziierten generischen Typ dar. Beispielsweise `Hashtable<K, V>` wird durch dargestellt `ICorDebugClass` , wohingegen `Hashtable<Int32, String>` von dargestellt wird `ICorDebugType` .  
  
 Nicht generische Typen werden sowohl von `ICorDebugClass` als auch von dargestellt `ICorDebugType` . Die zweite Schnittstelle wurde in der .NET Framework Version 2,0 eingeführt, um die Typinstanziierung zu behandeln.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
