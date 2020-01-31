---
title: ICorDebugProcess5::GetTypeLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: 306d881c05c2fcdb15a53a439bfce6eff3afffa8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792312"
---
# <a name="icordebugprocess5gettypelayout-method"></a>ICorDebugProcess5::GetTypeLayout-Methode
Ruft Informationen über das Layout eines Objekts im Arbeitsspeicher auf Grundlage des Typbezeichners ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>Parameters  
 `id`  
 in Ein [COR_TYPEID](cor-typeid-structure.md) Token, das den Typ angibt, dessen Layout gewünscht ist.  
  
 `pLayout`  
 vorgenommen Ein Zeiger auf eine [COR_TYPE_LAYOUT](cor-type-layout-structure.md) -Struktur, die Informationen über das Layout des-Objekts im Arbeitsspeicher enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugProcess5::GetTypeLayout`-Methode stellt Informationen zu einem Objekt bereit, das auf dem [COR_TYPEID](cor-typeid-structure.md)basiert, das von einer Reihe anderer [ICorDebugProcess5](icordebugprocess5-interface.md) -Methoden zurückgegeben wird. Die Informationen werden von einer [COR_TYPE_LAYOUT](cor-type-layout-structure.md) Struktur bereitgestellt, die von der-Methode aufgefüllt wird.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [COR_TYPE_LAYOUT-Struktur](cor-type-layout-structure.md)
- [ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
