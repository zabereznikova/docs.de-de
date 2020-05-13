---
title: ICorDebugSymbolProvider2-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: e6712dca776bf4c20ce7fc8568e94399a81beecb
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379301"
---
# <a name="icordebugsymbolprovider2-interface"></a>ICorDebugSymbolProvider2-Schnittstelle
Erweitert logisch die [icordebugsymbolprovider](icordebugsymbolprovider-interface.md) -Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetFrameProps-Methode](icordebugsymbolprovider2-getframeprops-method.md)|Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.|  
|[GetGenericDictionaryInfo-Methode](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|Ruft eine generische Wörterbuchzuordnung ab.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugSymbolProvider-Schnittstelle](icordebugsymbolprovider-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
