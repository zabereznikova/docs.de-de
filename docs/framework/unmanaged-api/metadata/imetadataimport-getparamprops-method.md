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
ms.openlocfilehash: bb73ccdd9eee4b5a655a56b5d6757e0c6003fbc9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437129"
---
# <a name="imetadataimportgetparamprops-method"></a>IMetaDataImport::GetParamProps-Methode
Ruft Metadatenwerte für den Parameter ab, auf den durch das angegebene ParamDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Ein ParamDef-Token, das den Parameter darstellt, für den Metadaten zurückgegeben werden sollen.  
  
 `pmd`  
 vorgenommen Ein Zeiger auf ein MethodDef-Token, das die Methode darstellt, die den-Parameter annimmt.  
  
 `pulSequence`  
 vorgenommen Die Ordinalposition des Parameters in der Methoden Argumentliste.  
  
 `szName`  
 vorgenommen Ein Puffer, der den Namen des Parameters enthalten soll.  
  
 `cchName`  
 in Die angeforderte Größe in breit Zeichen `szName`.  
  
 `pchName`  
 vorgenommen Die zurückgegebene Größe in breit Zeichen `szName`.  
  
 `pdwAttr`  
 vorgenommen Ein Zeiger auf alle Attributflags, die dem-Parameter zugeordnet sind. Dies ist eine Bitmaske von `CorParamAttr` Werten.  
  
 `pdwCPlusTypeFlag`  
 vorgenommen Ein Zeiger auf ein Flag, das angibt, dass der Parameter eine <xref:System.ValueType>ist.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf eine Konstante Zeichenfolge, die vom-Parameter zurückgegeben wird.  
  
 `pcchValue`  
 vorgenommen Die Größe der `ppValue` in breit Zeichen oder 0 (null), wenn `ppValue` keine Zeichenfolge enthält.  
  
## <a name="remarks"></a>Hinweise

Die Sequenzwerte in `pulSequence` mit 1 für Parameter beginnen. Ein Rückgabewert hat eine Sequenznummer von 0.

## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
