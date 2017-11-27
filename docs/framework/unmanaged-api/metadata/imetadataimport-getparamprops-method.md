---
title: IMetaDataImport::GetParamProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3f36282df52b316bfa32c50c3fa9f55f829aa04e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetparamprops-method"></a>IMetaDataImport::GetParamProps-Methode
Ruft Metadatenwerte für den Parameter ab, auf den durch das angegebene ParamDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `tk`  
 [in] Ein ParamDef-Token, die Metadaten für die zurückzugebenden Parameters darstellt.  
  
 `pmd`  
 [out] Ein Zeiger auf ein MethodDef-Token, das die Methode, die den Parameter akzeptiert darstellt.  
  
 `pulSequence`  
 [out] Die Ordnungsposition des Parameters in der Argumentliste der Methode.  
  
 `szName`  
 [out] Ein Puffer, der den Namen des Parameters enthält.  
  
 `cchName`  
 [in] Die angeforderte Größe in Breitzeichen `szName`.  
  
 `pchName`  
 [out] Die zurückgegebene Größe in Breitzeichen `szName`.  
  
 `pdwAttr`  
 [out] Ein Zeiger auf Attributflags, die dem Parameter zugeordnet.  
  
 `pdwCPlusTypeFlag`  
 [out] Ein Zeiger auf ein Flag, das angibt, die der Parameter ist ein <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Ein Zeiger auf eine Konstante Zeichenfolge, die durch den Parameter zurückgegeben.  
  
 `pcchValue`  
 [out] Die Größe des `ppValue` in Breitzeichen oder 0 (null), wenn `ppValue` errichtet keine Zeichenfolge.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
