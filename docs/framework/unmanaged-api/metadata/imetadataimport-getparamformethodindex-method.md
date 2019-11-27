---
title: IMetaDataImport::GetParamForMethodIndex-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
ms.openlocfilehash: a70691b9c519bc59ae7df7a86d5d6697db565575
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437165"
---
# <a name="imetadataimportgetparamformethodindex-method"></a>IMetaDataImport::GetParamForMethodIndex-Methode
Ruft das Token ab, das einen angegebenen Parameter der Methode darstellt, die durch das angegebene MethodDef-Token dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `md`  
 in Ein Token, das die Methode darstellt, für die das Parameter Token zurückgegeben werden soll.  
  
 `ulParamSeq`  
 in Die Ordinalposition in der Parameterliste, in der der angeforderte Parameter auftritt. Parameter werden beginnend mit 1 nummeriert, wobei der Rückgabewert der Methode an Position 0 (null) liegt.  
  
 `ppd`  
 vorgenommen Ein Zeiger auf ein ParamDef-Token, das den angeforderten Parameter darstellt.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
