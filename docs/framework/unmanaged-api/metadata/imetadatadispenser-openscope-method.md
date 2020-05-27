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
ms.openlocfilehash: 8d9de753f1c44338a96e990def80643d591f2a8b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007467"
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
 in Ein Wert der [CorOpenFlags](coropenflags-enumeration.md) -Enumeration, mit dem der Modus (lesen, schreiben usw.) zum Öffnen angegeben wird.  
  
 `riid`  
 in Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll. der Aufrufer verwendet die-Schnittstelle, um Metadaten zu importieren (lesen) oder auszugeben (schreiben).  
  
 Der Wert von `riid` muss eine der Schnittstellen "Import" oder "ausgeben" angeben. Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.  
  
 `ppIUnk`  
 vorgenommen Der Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Die in-Memory-Kopie der Metadaten kann mithilfe von Methoden einer der "Import"-Schnittstellen abgefragt oder mithilfe von Methoden aus einer der "Ausgabe"-Schnittstellen hinzugefügt werden.  
  
 Wenn die Zieldatei keine CLR-Metadaten enthält, kann die Methode nicht ausgeführt `OpenScope` werden.  
  
 Wenn in der .NET Framework Version 1,0 und Version 1,1 ein Bereich geöffnet wird und `dwOpenFlags` auf ofRead festgelegt ist, ist er für die Freigabe berechtigt. Das heißt, wenn nachfolgende Aufrufe `OpenScope` von den Namen einer Datei übergeben, die zuvor geöffnet war, wird der vorhandene Bereich wieder verwendet, und es wird kein neuer Satz von Datenstrukturen erstellt. Probleme können jedoch aufgrund dieser Freigabe auftreten.  
  
 In der Version 2,0 von .NET Framework werden Bereiche, `dwOpenFlags` die mit auf ofRead festgelegt wurden, nicht mehr freigegeben. Verwenden Sie den ofReadOnly-Wert, damit der Bereich freigegeben werden kann. Wenn ein Bereich freigegeben wird, schlagen Abfragen, die "Lese-/Schreib-Metadatenschnittstellen" verwenden, fehl.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataDispenser-Schnittstelle](imetadatadispenser-interface.md)
- [IMetaDataDispenserEx-Schnittstelle](imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
