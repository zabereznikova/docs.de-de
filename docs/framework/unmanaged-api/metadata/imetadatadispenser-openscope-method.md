---
title: IMetaDataDispenser::OpenScope-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5ce1af82631531f8f7105fbf92ba78db3cca437b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442332"
---
# <a name="imetadatadispenseropenscope-method"></a>IMetaDataDispenser::OpenScope-Methode
Öffnet eine vorhandene Datei auf dem Datenträger und ordnet Ihre Metadaten dem Arbeitsspeicher zu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `szScope`  
 in Der Name der Datei, die geöffnet werden soll. Die Datei muss Common Language Runtime (CLR)-Metadaten enthalten.  
  
 `dwOpenFlags`  
 in Ein Wert der [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) -Enumeration, mit dem der Modus (lesen, schreiben usw.) zum Öffnen angegeben wird.  
  
 `riid`  
 in Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll. der Aufrufer verwendet die-Schnittstelle, um Metadaten zu importieren (lesen) oder auszugeben (schreiben).  
  
 Der Wert `riid` muss eine der Schnittstellen "Import" oder "ausgeben" angeben. Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.  
  
 `ppIUnk`  
 vorgenommen Der Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Die in-Memory-Kopie der Metadaten kann mithilfe von Methoden einer der "Import"-Schnittstellen abgefragt oder mithilfe von Methoden aus einer der "Ausgabe"-Schnittstellen hinzugefügt werden.  
  
 Wenn die Zieldatei keine CLR-Metadaten enthält, kann die `OpenScope` Methode nicht ausgeführt werden.  
  
 Wenn in der .NET Framework Version 1,0 und Version 1,1 ein Bereich geöffnet wird, für den `dwOpenFlags` auf ofRead festgelegt ist, ist er für die Freigabe berechtigt. Das heißt, wenn bei nachfolgenden Aufrufen von `OpenScope` der Name einer zuvor geöffneten Datei übergeben wird, wird der vorhandene Bereich wieder verwendet, und es wird kein neuer Satz von Datenstrukturen erstellt. Probleme können jedoch aufgrund dieser Freigabe auftreten.  
  
 In der .NET Framework Version 2,0 werden Bereiche, die mit `dwOpenFlags` auf ofRead festgelegt wurden, nicht mehr freigegeben. Verwenden Sie den ofReadOnly-Wert, damit der Bereich freigegeben werden kann. Wenn ein Bereich freigegeben wird, schlagen Abfragen, die "Lese-/Schreib-Metadatenschnittstellen" verwenden, fehl.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
