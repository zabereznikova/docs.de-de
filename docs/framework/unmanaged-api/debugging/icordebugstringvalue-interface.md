---
title: ICorDebugStringValue Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2814f6164f383c36bb5b8e20ce8996b30eef0f1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421699"
---
# <a name="icordebugstringvalue-interface1"></a>ICorDebugStringValue Schnittstelle1
Eine Unterklasse von ICorDebugHeapValue, die für Zeichenfolgenwerte gilt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetLength-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|Ruft die Anzahl der Zeichen in der Zeichenfolge, die auf die verwiesen wird von diesem `ICorDebugStringValue`.|  
|[GetString-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|Ruft die Zeichenfolge, die auf die verwiesen wird von diesem `ICorDebugStringValue`.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
