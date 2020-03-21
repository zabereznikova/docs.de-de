---
title: IMetaDataDispenser::OpenScopeOnMemory-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 492c37540ad68b5b134520218eedc59013c68519
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175927"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>IMetaDataDispenser::OpenScopeOnMemory-Methode
Öffnet einen Speicherbereich, der vorhandene Metadaten enthält. Das heißt, diese Methode öffnet einen angegebenen Speicherbereich, in dem die vorhandenen Daten als Metadaten behandelt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pData`  
 [in] Ein Zeiger, der die Startadresse des Speicherbereichs angibt.  
  
 `cbData`  
 [in] Die Größe des Speicherbereichs in Bytes.  
  
 `dwOpenFlags`  
 [in] Ein Wert der CorOpenFlags-Enumeration, um den Modus (Lesen, Schreiben usw.) zum Öffnen anzugeben. [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)  
  
 `riid`  
 [in] Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll; Der Aufrufer verwendet die Schnittstelle, um Metadaten zu importieren (lesen) oder auszusenden (schreiben).  
  
 Der Wert `riid` von muss eine der Schnittstellen "import" oder "emit" angeben. Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.  
  
 `ppIUnk`  
 [out] Der Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="remarks"></a>Bemerkungen  
 Die In-Memory-Kopie der Metadaten kann mithilfe von Methoden von einer der "Import"-Schnittstellen abgefragt oder mit Methoden aus einer der "emit"-Schnittstellen hinzugefügt werden.  
  
 Die `OpenScopeOnMemory` Methode ähnelt der [IMetaDataDispenser::OpenScope-Methode,](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) mit der Ausnahme, dass die Metadaten, die von Interesse sind, bereits im Arbeitsspeicher und nicht in einer Datei auf dem Datenträger vorhanden sind.  
  
 Wenn der Zielspeicherbereich keine CLR-Metadaten (Common Language `OpenScopeOnMemory` Runtime) enthält, schlägt die Methode fehl.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
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
