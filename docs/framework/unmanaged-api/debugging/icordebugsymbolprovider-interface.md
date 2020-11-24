---
title: ICorDebugSymbolProvider-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: ff1f39be3d3db43f70cfa4a0711a3f42c180bc1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672083"
---
# <a name="icordebugsymbolprovider-interface"></a>ICorDebugSymbolProvider-Schnittstelle

Stellt Methoden bereit, die zum Abrufen von Debugsymbolinformationen verwendet werden können.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetAssemblyImageBytes-Methode](icordebugsymbolprovider-getassemblyimagebytes-method.md)|Liest Daten aus einer zusammengeführten Assembly, wenn eine relative virtuelle Adresse (RVA) in der zusammengeführten Assembly angegeben ist.|  
|[GetAssemblyImageMetadata-Methode](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|Gibt die Metadaten aus einer zusammengeführten Assembly zurück.|  
|[GetCodeRange-Methode](icordebugsymbolprovider-getcoderange-method.md)|Ruft die Startadresse und Größe einer Methode ab, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.|  
|[GetInstanceFieldSymbols-Methode](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|Ruft die Instanzenfeldsymbole ab, die einer TypeSpec-Signatur entsprechen.|  
|[GetMergedAssemblyRecords-Methode](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|Ruft die Symboldatensätze für alle zusammengeführten Assemblys ab.|  
|[GetMethodLocalSymbols-Methode](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|Ruft die lokalen Symbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.|  
|[GetMethodParameterSymbols-Methode](icordebugsymbolprovider-getmethodparametersymbols-method.md)|Ruft die Parametersymbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.|  
|[GetMethodProps-Methode](icordebugsymbolprovider-getmethodprops-method.md)|Gibt Informationen zu Methodeneigenschaften wie das Metadatentoken der Methode und Informationen zu den generischen Parametern der Methode zurück, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.|  
|[GetObjectSize-Methode](icordebugsymbolprovider-getobjectsize-method.md)|Gibt die Objektgröße eines Objekts basierend auf seiner TypeSpec-Signatur zurück.|  
|[GetStaticFieldSymbols-Methode](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|Ruft die statischen Feldsymbole ab, die einer TypeSpec-Signatur entsprechen.|  
|[GetTypeProps-Methode](icordebugsymbolprovider-gettypeprops-method.md)|Gibt anhand einer relativen virtuellen Adresse (RVA) in einem VTable Informationen zu den Eigenschaften eines Typs wie die Anzahl der Signaturen der generischen Parameter zurück.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
