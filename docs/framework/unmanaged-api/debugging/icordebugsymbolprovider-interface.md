---
title: ICorDebugSymbolProvider-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: fb947fec8f17fe13374251b4429be798a335eed6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133660"
---
# <a name="icordebugsymbolprovider-interface"></a>ICorDebugSymbolProvider-Schnittstelle
Stellt Methoden bereit, die zum Abrufen von Debugsymbolinformationen verwendet werden können.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetAssemblyImageBytes-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagebytes-method.md)|Liest Daten aus einer zusammengeführten Assembly, wenn eine relative virtuelle Adresse (RVA) in der zusammengeführten Assembly angegeben ist.|  
|[GetAssemblyImageMetadata-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagemetadata-method.md)|Gibt die Metadaten aus einer zusammengeführten Assembly zurück.|  
|[GetCodeRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getcoderange-method.md)|Ruft die Startadresse und Größe einer Methode ab, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.|  
|[GetInstanceFieldSymbols-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)|Ruft die Instanzenfeldsymbole ab, die einer TypeSpec-Signatur entsprechen.|  
|[GetMergedAssemblyRecords-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmergedassemblyrecords-method.md)|Ruft die Symboldatensätze für alle zusammengeführten Assemblys ab.|  
|[GetMethodLocalSymbols-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)|Ruft die lokalen Symbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.|  
|[GetMethodParameterSymbols-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)|Ruft die Parametersymbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.|  
|[GetMethodProps-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)|Gibt Informationen zu Methodeneigenschaften wie das Metadatentoken der Methode und Informationen zu den generischen Parametern der Methode zurück, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.|  
|[GetObjectSize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getobjectsize-method.md)|Gibt die Objektgröße eines Objekts basierend auf seiner TypeSpec-Signatur zurück.|  
|[GetStaticFieldSymbols-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)|Ruft die statischen Feldsymbole ab, die einer TypeSpec-Signatur entsprechen.|  
|[GetTypeProps-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)|Gibt anhand einer relativen virtuellen Adresse (RVA) in einem VTable Informationen zu den Eigenschaften eines Typs wie die Anzahl der Signaturen der generischen Parameter zurück.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
