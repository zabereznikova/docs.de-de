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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e1be6079ed382b8ab27d0aec16bd725f5c5b9cb5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778907"
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
 [in] Ein FieldDef oder MethodDef-Token zum Abrufen von Metadaten die PInvoke-Zuordnung für.  
  
 `pdwMappingFlags`  
 [out] Ein Zeiger auf Bitflags, die für die Zuordnung. Dieser Wert ist eine Bitmaske aus der [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) Enumeration.  
  
 `szImportName`  
 [out] Der Name des nicht verwalteten Ziel-DLL.  
  
 `cchImportName`  
 [in] Die Größe in Breitzeichen `szImportName`.  
  
 `pchImportName`  
 [out] Die Anzahl der Breitzeichen, die in zurückgegebenen `szImportName`.  
  
 `pmrImportDLL`  
 [out] Ein Zeiger auf ein ModuleRef-Token, die nicht verwaltete Objekt Zielbibliothek darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
