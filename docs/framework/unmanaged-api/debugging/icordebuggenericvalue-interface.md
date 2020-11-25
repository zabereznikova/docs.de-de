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
ms.openlocfilehash: cfa0950ca2ef4e969258c147b762fa95e52a82e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705814"
---
# <a name="icordebuggenericvalue-interface"></a>ICorDebugGenericValue-Schnittstelle

Eine Unterklasse von "ICorDebugValue", die für alle Werte gilt. Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetValue-Methode](icordebuggenericvalue-getvalue-method.md)|Kopiert den Wert in den angegebenen Puffer.|  
|[SetValue-Methode](icordebuggenericvalue-setvalue-method.md)|Kopiert einen neuen Wert aus dem angegebenen Puffer.|  
  
## <a name="remarks"></a>Hinweise  

 `ICorDebugGenericValue` ist eine untergeordnete Schnittstelle, da Sie nicht Remote fähig ist.  
  
 Bei Verweis Typen ist der Wert der Verweis und nicht der Inhalt des Verweises.  
  
 Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
