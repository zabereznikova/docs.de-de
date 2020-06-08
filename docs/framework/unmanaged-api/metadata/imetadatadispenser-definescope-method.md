---
title: IMetaDataDispenser::DefineScope-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 12a32b5d2f0647ea2d9b696d08d6644e30be0c65
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501364"
---
# <a name="imetadatadispenserdefinescope-method"></a>IMetaDataDispenser::DefineScope-Methode
Erstellt einen neuen Bereich im Arbeitsspeicher, in dem Sie neue Metadaten erstellen können.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `rclsid`  
 in Die CLSID der Version der zu erstellenden Metadatenstrukturen. Dieser Wert muss für die .NET Framework Version 2,0 CLSID_CorMetaDataRuntime werden.  
  
 `dwCreateFlags`  
 in Flags, die Optionen angeben. Dieser Wert muss für den .NET Framework 2,0 den Wert 0 (null) aufweisen.  
  
 `riid`  
 in Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll. der Aufrufer verwendet die-Schnittstelle, um die neuen Metadaten zu erstellen.  
  
 Der Wert von `riid` muss eine der "Auswertungs Schnittstellen" angeben. Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit oder IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 vorgenommen Der Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="remarks"></a>Bemerkungen  
 `DefineScope`erstellt eine Gruppe von in-Memory-Metadatentabellen, generiert eine eindeutige GUID (Modul Versions Bezeichner oder MVID) für die Metadaten und erstellt einen Eintrag in der Modul Tabelle für die ausgegebene Kompilierungseinheit.  
  
 Sie können Attribute an den Metadatenbereich als Ganzes anfügen, indem Sie je nach Bedarf die [IMetaDataEmit:: setmodulerequior](imetadataemit-setmoduleprops-method.md) [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md) -Methode verwenden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataDispenser-Schnittstelle](imetadatadispenser-interface.md)
- [IMetaDataDispenserEx-Schnittstelle](imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
