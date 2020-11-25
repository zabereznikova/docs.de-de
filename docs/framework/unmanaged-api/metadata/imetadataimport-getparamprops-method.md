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
ms.openlocfilehash: a16621f4c9b06f049239dc4e2335d70a167dd756
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729264"
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
 in Die angeforderte Größe in breit Zeichen von `szName` .  
  
 `pchName`  
 vorgenommen Die zurückgegebene Größe in breit Zeichen von `szName` .  
  
 `pdwAttr`  
 vorgenommen Ein Zeiger auf alle Attributflags, die dem-Parameter zugeordnet sind. Dies ist eine Bitmaske von `CorParamAttr` Werten.  
  
 `pdwCPlusTypeFlag`  
 vorgenommen Ein Zeiger auf ein Flag, das angibt, dass der-Parameter ein ist <xref:System.ValueType> .  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf eine Konstante Zeichenfolge, die vom-Parameter zurückgegeben wird.  
  
 `pcchValue`  
 vorgenommen Die Größe von `ppValue` in breit Zeichen oder 0 (null), wenn `ppValue` keine Zeichenfolge enthält.  
  
## <a name="remarks"></a>Hinweise

Die Sequenzwerte in `pulSequence` beginnen mit 1 für Parameter. Ein Rückgabewert hat eine Sequenznummer von 0.

## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
