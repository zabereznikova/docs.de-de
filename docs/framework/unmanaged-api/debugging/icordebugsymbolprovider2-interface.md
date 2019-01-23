---
title: ICorDebugSymbolProvider2-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea60ecd542300bf3833c4977b7f0910399a2e409
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504027"
---
# <a name="icordebugsymbolprovider2-interface"></a>ICorDebugSymbolProvider2-Schnittstelle
Erweitert logisch die [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetFrameProps-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.|  
|[GetGenericDictionaryInfo-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|Ruft eine generische Wörterbuchzuordnung ab.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugSymbolProvider-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
