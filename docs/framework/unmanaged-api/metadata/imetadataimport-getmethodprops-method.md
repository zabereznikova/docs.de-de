---
title: IMetaDataImport::GetMethodProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 0eb4e9d713581cf32cec18bb02a6bd13542e517a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733181"
---
# <a name="imetadataimportgetmethodprops-method"></a>IMetaDataImport::GetMethodProps-Methode

Ruft die Metadaten ab, die der Methode zugeordnet sind, auf die durch das angegebene MethodDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `mb`  
 in Das MethodDef-Token, das die Methode darstellt, für die Metadaten zurückgegeben werden sollen.  
  
 `pClass`  
 vorgenommen Ein Zeiger auf ein TypeDef-Token, das den Typ darstellt, der die Methode implementiert.  
  
 `szMethod`  
 vorgenommen Ein Zeiger auf einen Puffer, der den Methodennamen aufweist.  
  
 `cchMethod`  
 in Die angeforderte Größe von `szMethod` .  
  
 `pchMethod`  
 vorgenommen Ein Zeiger auf die Größe in breit Zeichen von `szMethod` oder im Fall von abschneiden die tatsächliche Anzahl von breit Zeichen im Methodennamen.  
  
 `pdwAttr`  
 vorgenommen Ein Zeiger auf alle Flags, die der Methode zugeordnet sind.  
  
 `ppvSigBlob`  
 vorgenommen Ein Zeiger auf die binäre Metadatensignatur der Methode.  
  
 `pcbSigBlob`  
 vorgenommen Ein Zeiger auf die Größe in Byte `ppvSigBlob` .  
  
 `pulCodeRVA`  
 vorgenommen Ein Zeiger auf die relative virtuelle Adresse der Methode.  
  
 `pdwImplFlags`  
 vorgenommen Ein Zeiger auf alle Implementierungsflags für die Methode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
