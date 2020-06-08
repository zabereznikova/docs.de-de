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
ms.openlocfilehash: 21a83e404405ca9cfe301b76cb1e1591d69e747c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491120"
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
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
