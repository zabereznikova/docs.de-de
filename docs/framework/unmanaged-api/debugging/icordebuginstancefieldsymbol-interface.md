---
title: ICorDebugInstanceFieldSymbol-Schnittstelle
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 4ef0f7a46acf7e9df732d630c9eb22044e09d658
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724896"
---
# <a name="icordebuginstancefieldsymbol-interface"></a>ICorDebugInstanceFieldSymbol-Schnittstelle

Stellt die Debugsymbolinformationen für ein Instanzfeld dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetName-Methode](icordebuginstancefieldsymbol-getname-method.md)|Ruft den Namen des Instanzfelds ab.|  
|[GetOffset-Methode](icordebuginstancefieldsymbol-getoffset-method.md)|Ruft den Offset dieses Instanzenfelds in der übergeordneten Klasse in Bytes ab.|  
|[GetSize-Methode](icordebuginstancefieldsymbol-getsize-method.md)|Ruft die Größe des Instanzfelds in Bytes ab.|  
  
## <a name="remarks"></a>Hinweise  

 Die `ICorDebugInstanceFieldSymbol`-Schnittstelle wird verwendet, um Debugsymbolinformationen für ein Instanzfeld abzurufen.  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugStaticFieldSymbol-Schnittstelle](icordebugstaticfieldsymbol-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
