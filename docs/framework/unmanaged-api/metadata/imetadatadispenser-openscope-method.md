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
ms.openlocfilehash: 5185fb6663910c85ce5dae1225b9b10c5dd8bb28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175940"
---
# <a name="imetadatadispenseropenscope-method"></a>IMetaDataDispenser::OpenScope-Methode
Öffnet eine vorhandene Datei auf der Festplatte und ordnet ihre Metadaten dem Speicher zu.  
  
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
 [in] Der Name der zu öffnenden Datei. Die Datei muss CLR-Metadaten (Common Language Runtime) enthalten.  
  
 `dwOpenFlags`  
 [in] Ein Wert der CorOpenFlags-Enumeration, um den Modus (Lesen, Schreiben usw.) zum Öffnen anzugeben. [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)  
  
 `riid`  
 [in] Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll; Der Aufrufer verwendet die Schnittstelle, um Metadaten zu importieren (lesen) oder auszusenden (schreiben).  
  
 Der Wert `riid` von muss eine der Schnittstellen "import" oder "emit" angeben. Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.  
  
 `ppIUnk`  
 [out] Der Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="remarks"></a>Bemerkungen  
 Die In-Memory-Kopie der Metadaten kann mithilfe von Methoden von einer der "Import"-Schnittstellen abgefragt oder mit Methoden aus einer der "emit"-Schnittstellen hinzugefügt werden.  
  
 Wenn die Zieldatei keine CLR-Metadaten enthält, schlägt die `OpenScope` Methode fehl.  
  
 Wenn in .NET Framework Version 1.0 und Version 1.1 ein Bereich mit `dwOpenFlags` Satz auf Read geöffnet wird, kann er freigegeben werden. Das heißt, wenn `OpenScope` nachfolgende Aufrufe im Namen einer zuvor geöffneten Datei übergeben werden, wird der vorhandene Bereich wiederverwendet, und es wird kein neuer Satz von Datenstrukturen erstellt. Aufgrund dieser Freigabe können jedoch Probleme auftreten.  
  
 In .NET Framework Version 2.0 werden `dwOpenFlags` Bereiche, die mit Set auf Read geöffnet wurden, nicht mehr freigegeben. Verwenden Sie den Wert ofReadOnly, damit der Bereich freigegeben werden kann. Wenn ein Bereich freigegeben wird, schlagen Abfragen fehl, die "Lese-/Schreib"-Metadatenschnittstellen verwenden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
