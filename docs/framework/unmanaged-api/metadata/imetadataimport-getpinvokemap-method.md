---
title: IMetaDataImport::GetPinvokeMap-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
ms.openlocfilehash: c458fef77b49f522ca21dd5487731f4d43588cea
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437097"
---
# <a name="imetadataimportgetpinvokemap-method"></a>IMetaDataImport::GetPinvokeMap-Methode
Ruft ein ModuleRef-Token zum Darstellen der Zielassembly eines PInvoke-Aufrufs ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tk`  
 in Ein FieldDef-oder MethodDef-Token, für das die PInvoke-Mapping-Metadaten zu erhalten sind.  
  
 `pdwMappingFlags`  
 vorgenommen Ein Zeiger auf Flags, die für die Zuordnung verwendet werden. Dieser Wert ist eine Bitmaske aus der [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) -Enumeration.  
  
 `szImportName`  
 vorgenommen Der Name der nicht verwalteten Ziel-dll.  
  
 `cchImportName`  
 in Die Größe in breit Zeichen `szImportName`.  
  
 `pchImportName`  
 vorgenommen Die Anzahl der breit Zeichen, die in `szImportName`zurückgegeben werden.  
  
 `pmrImportDLL`  
 vorgenommen Ein Zeiger auf ein ModuleRef-Token, das die nicht verwaltete Zielobjekt Bibliothek darstellt.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
