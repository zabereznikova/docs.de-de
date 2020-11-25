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
ms.openlocfilehash: 26293e38a275ca691c7d48dceb12c1e7dd316536
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713417"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>IMetaDataDispenser::OpenScopeOnMemory-Methode

Öffnet einen Arbeitsspeicher Bereich, der vorhandene Metadaten enthält. Das heißt, diese Methode öffnet einen angegebenen Bereich des Speichers, in dem die vorhandenen Daten als Metadaten behandelt werden.  
  
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
 in Ein-Zeiger, der die Startadresse des Speicherbereichs angibt.  
  
 `cbData`  
 in Die Größe des Arbeitsspeicher Bereichs in Bytes.  
  
 `dwOpenFlags`  
 in Ein Wert der [CorOpenFlags](coropenflags-enumeration.md) -Enumeration, mit dem der Modus (lesen, schreiben usw.) zum Öffnen angegeben wird.  
  
 `riid`  
 in Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll. der Aufrufer verwendet die-Schnittstelle, um Metadaten zu importieren (lesen) oder auszugeben (schreiben).  
  
 Der Wert von `riid` muss eine der Schnittstellen "Import" oder "ausgeben" angeben. Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.  
  
 `ppIUnk`  
 vorgenommen Der Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  

 Die in-Memory-Kopie der Metadaten kann mithilfe von Methoden einer der "Import"-Schnittstellen abgefragt oder mithilfe von Methoden aus einer der "Ausgabe"-Schnittstellen hinzugefügt werden.  
  
 Die- `OpenScopeOnMemory` Methode ähnelt der [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) -Methode, mit der Ausnahme, dass die relevanten Metadaten bereits im Arbeitsspeicher vorhanden sind, und nicht in einer Datei auf dem Datenträger.  
  
 Wenn der Zielspeicher Bereich keine Common Language Runtime (CLR)-Metadaten enthält, schlägt die `OpenScopeOnMemory` Methode fehl.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataDispenser-Schnittstelle](imetadatadispenser-interface.md)
- [IMetaDataDispenserEx-Schnittstelle](imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
