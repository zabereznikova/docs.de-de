---
title: IMetaDataImport2::GetGenericParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: 7e97b2d4ad1fec4675d1484959b115a4d4b87e90
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490613"
---
# <a name="imetadataimport2getgenericparamprops-method"></a>IMetaDataImport2::GetGenericParamProps-Methode
Ruft die Metadaten ab, die dem durch das angegebene Token dargestellten generischen Parameter zugeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `gp`  
 in Das Token, das den generischen Parameter darstellt, für den Metadaten zurückgegeben werden sollen.  
  
 `pulParamSeq`  
 vorgenommen Die Ordinalposition des `Type` Parameters im übergeordneten Konstruktor oder in der Methode.  
  
 `pdwParamFlags`  
 vorgenommen Ein Wert der [CorGenericParamAttr](corgenericparamattr-enumeration.md) -Enumeration, der die `Type` für den generischen Parameter beschreibt.  
  
 `ptOwner`  
 vorgenommen Ein TypeDef-oder MethodDef-Token, das den Besitzer des Parameters darstellt.  
  
 `reserved`  
 vorgenommen Reserviert für zukünftige Erweiterbarkeit.  
  
 `wzName`  
 vorgenommen Der Name des generischen Parameters.  
  
 `cchName`  
 in Die Größe des `wzName` Puffers.  
  
 `pchName`  
 vorgenommen Die zurückgegebene Größe des Namens in breit Zeichen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
