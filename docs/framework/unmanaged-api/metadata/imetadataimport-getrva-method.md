---
title: IMetaDataImport::GetRVA-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: 58ab9ee9381fce4d7af1910df6c8d3bb813bcf13
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490890"
---
# <a name="imetadataimportgetrva-method"></a>IMetaDataImport::GetRVA-Methode
Ruft die relative virtuelle Adresse (RVA) und die Implementierungsflags der Methode oder des Felds ab, die durch das angegebene Token dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tk`  
 in Ein MethodDef-oder FieldDef-Metadatentoken, das das Code Objekt darstellt, für das die RVA zurückgegeben werden soll. Wenn das Token ein FieldDef-Token ist, muss es sich bei dem Feld um eine globale Variable handeln.  
  
 `pulCodeRVA`  
 vorgenommen Ein Zeiger auf die relative virtuelle Adresse des Code Objekts, das durch das Token dargestellt wird.  
  
 `pdwImplFlags`  
 vorgenommen Ein Zeiger auf die Implementierungsflags für die Methode. Dieser Wert ist eine Bitmaske aus der [CorMethodImpl](cormethodimpl-enumeration.md) -Enumeration. Der Wert von `pdwImplFlags` ist nur gültig, wenn `tk` ein MethodDef-Token ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
