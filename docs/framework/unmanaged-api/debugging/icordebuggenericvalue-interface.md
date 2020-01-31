---
title: ICorDebugGenericValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: e60d4b128bf03ff81863e0c95815b2c204807583
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794472"
---
# <a name="icordebuggenericvalue-interface"></a>ICorDebugGenericValue-Schnittstelle

Eine Unterklasse von "ICorDebugValue", die für alle Werte gilt. Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetValue-Methode](icordebuggenericvalue-getvalue-method.md)|Kopiert den Wert in den angegebenen Puffer.|  
|[SetValue-Methode](icordebuggenericvalue-setvalue-method.md)|Kopiert einen neuen Wert aus dem angegebenen Puffer.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugGenericValue` ist eine Unterschnittstelle, da Sie nicht Remote fähig ist.  
  
 Bei Verweis Typen ist der Wert der Verweis und nicht der Inhalt des Verweises.  
  
 Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
