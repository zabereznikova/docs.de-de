---
title: ICorDebugStringValue-Schnittstelle
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
ms.openlocfilehash: d1d3a5eb6e0b24b40a35c13a99465dd3c7032a91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138941"
---
# <a name="icordebugstringvalue-interface"></a>ICorDebugStringValue-Schnittstelle
Eine Unterklasse von ICorDebugHeapValue, die auf Zeichen folgen Werte angewendet wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetLength-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|Ruft die Anzahl der Zeichen in der Zeichenfolge ab, auf die von diesem `ICorDebugStringValue`verwiesen wird.|  
|[GetString-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|Ruft die Zeichenfolge ab, auf die diese `ICorDebugStringValue`verweist.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
