---
title: IMetaDataImport::GetParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05ac8efed8c0a905d2cfad433348a99fe578eeae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153178"
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
  
## <a name="parameters"></a>Parameter  
 `tk`  
 [in] Ein ParamDef-Token, das die Parameter für die Metadaten zurückgegeben darstellt.  
  
 `pmd`  
 [out] Ein Zeiger auf ein MethodDef-Token, das die Methode, die den Parameter akzeptiert darstellt.  
  
 `pulSequence`  
 [out] Die Ordnungsposition des Parameters in der Argumentliste für die Methode.  
  
 `szName`  
 [out] Ein Puffer, der den Namen des Parameters enthält.  
  
 `cchName`  
 [in] Die angeforderte Größe in Breitzeichen `szName`.  
  
 `pchName`  
 [out] Die zurückgegebene Größe in Breitzeichen `szName`.  
  
 `pdwAttr`  
 [out] Ein Zeiger auf die Attributflags, die dem Parameter zugeordnet. Dies ist eine Bitmaske der `CorParamAttr` Werte.  
  
 `pdwCPlusTypeFlag`  
 [out] Ein Zeiger auf ein Flag, der angibt, der Parameter ist, ein <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Ein Zeiger auf eine Konstante Zeichenfolge, die durch den Parameter zurückgegeben.  
  
 `pcchValue`  
 [out] Die Größe des `ppValue` in Breitzeichen oder NULL, wenn `ppValue` errichtet keine Zeichenfolge.  
  
## <a name="remarks"></a>Hinweise

Die Sequenzwerte `pulSequence` beginnen mit 1 für Parameter. Ein Wert zurückgegeben hat eine Sequenznummer 0.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
