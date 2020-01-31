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
ms.openlocfilehash: 7ac588591222a1abbc7b99ec7e973284c055f95e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784168"
---
# <a name="icordebugclass-interface"></a>ICorDebugClass-Schnittstelle

Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann. Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetModule-Methode](icordebugclass-getmodule-method.md)|Ruft das Modul ab, das diese Klasse definiert.|  
|[GetStaticFieldValue-Methode](icordebugclass-getstaticfieldvalue-method.md)|Ruft den Wert des angegebenen statischen Felds ab.|  
|[GetToken-Methode](icordebugclass-gettoken-method.md)|Ruft das `TypeDef` Metadatentoken für diese Klasse ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugClass`-Schnittstelle stellt einen nicht instanziierten generischen Typ dar. Die ICorDebugType-Schnittstelle stellt einen instanziierten generischen Typ dar. Beispielsweise wird `Hashtable<K, V>` durch `ICorDebugClass`dargestellt, wohingegen `Hashtable<Int32, String>` durch `ICorDebugType`dargestellt würde.  
  
 Nicht generische Typen werden durch `ICorDebugClass` und `ICorDebugType`dargestellt. Die zweite Schnittstelle wurde in der .NET Framework Version 2,0 eingeführt, um die Typinstanziierung zu behandeln.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
