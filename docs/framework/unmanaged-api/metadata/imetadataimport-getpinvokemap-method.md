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
ms.openlocfilehash: 8409e56b5ec4dbe47035a0555b6b7ce175b517ee
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490977"
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
 vorgenommen Ein Zeiger auf Flags, die für die Zuordnung verwendet werden. Dieser Wert ist eine Bitmaske aus der [CorPinvokeMap](corpinvokemap-enumeration.md) -Enumeration.  
  
 `szImportName`  
 vorgenommen Der Name der nicht verwalteten Ziel-dll.  
  
 `cchImportName`  
 in Die Größe in breit Zeichen von `szImportName` .  
  
 `pchImportName`  
 vorgenommen Die Anzahl der breit Zeichen, die in zurückgegeben werden `szImportName` .  
  
 `pmrImportDLL`  
 vorgenommen Ein Zeiger auf ein ModuleRef-Token, das die nicht verwaltete Zielobjekt Bibliothek darstellt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
