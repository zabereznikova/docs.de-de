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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1763f9341af2d90cf465cb554bf7f282a4d92058
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777810"
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
 [in] Die CLSID der Version von Systemmetadaten-Strukturen erstellt werden. Dieser Wert muss es sich um CLSID_CorMetaDataRuntime für .NET Framework, Version 2.0 sein.  
  
 `dwCreateFlags`  
 [in] Flags, die Optionen angeben. Dieser Wert muss 0 (null) für .NET Framework 2.0 sein.  
  
 `riid`  
 [in] Die IID der Metadatenschnittstelle gewünschten zurückgegeben werden; der Aufrufer wird die Schnittstelle verwenden, um die neuen Metadaten zu erstellen.  
  
 Der Wert des `riid` müssen eine der Schnittstellen "Ausgabe" angeben. Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit oder IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 [out] Der Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 `DefineScope` erstellt einen Satz von in-Memory-Tabellen, generiert eine eindeutige GUID für die Metadaten (Modul Versions-ID oder MVID) und erstellt einen Eintrag in der Modultabelle für die Kompilierungseinheit ausgegeben wird.  
  
 Sie können Attribute als Ganzes an den Metadatenbereich anfügen, indem Sie mit der [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) oder [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) Methode, nach Bedarf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
