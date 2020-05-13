---
title: ICorDebugStaticFieldSymbol-Schnittstelle
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: f9b82f0f98a668555a8096d7575c049c31cae93a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379440"
---
# <a name="icordebugstaticfieldsymbol-interface"></a>ICorDebugStaticFieldSymbol-Schnittstelle
Stellt die Debugsymbolinformationen für ein statisches Feld dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetAddress-Methode](icordebugstaticfieldsymbol-getaddress-method.md)|Ruft die Adresse des statischen Felds ab.|  
|[GetName-Methode](icordebugstaticfieldsymbol-getname-method.md)|Ruft den Namen des statischen Felds ab.|  
|[GetSize-Methode](icordebugstaticfieldsymbol-getsize-method.md)|Ruft die Größe des statischen Felds in Bytes ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugStaticFieldSymbol`-Schnittstelle wird verwendet, um Debugsymbolinformationen für ein statisches Feld abzurufen.  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugInstanceFieldSymbol-Schnittstelle](icordebuginstancefieldsymbol-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
