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
ms.openlocfilehash: 190bcacc84646cfd9294cf2b6b53b0474f38758f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177217"
---
# <a name="imetadataimportgetrva-method"></a>IMetaDataImport::GetRVA-Methode
Ruft die relative virtuelle Adresse (RVA) und die Implementierungsflags der Methode oder des Felds ab, die durch das angegebene Token dargestellt werden.  
  
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
 [in] Ein MethodDef- oder FieldDef-Metadatentoken, das das Codeobjekt darstellt, für das die RVA zurückgegeben werden soll. Wenn es sich bei dem Token um ein FieldDef handelt, muss es sich bei dem Feld um eine globale Variable handelt.  
  
 `pulCodeRVA`  
 [out] Ein Zeiger auf die relative virtuelle Adresse des Codeobjekts, das durch das Token dargestellt wird.  
  
 `pdwImplFlags`  
 [out] Ein Zeiger auf die Implementierungsflags für die Methode. Dieser Wert ist eine Bitmaske aus der [CorMethodImpl-Enumeration.](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) Der Wert `pdwImplFlags` von ist `tk` nur gültig, wenn es sich um ein MethodDef-Token handelt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
