---
title: IMetaDataImport::GetNameFromToken-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
ms.openlocfilehash: 6ed30f07fcec9c730e1514350c594399f0aa16e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437275"
---
# <a name="imetadataimportgetnamefromtoken-method"></a>IMetaDataImport::GetNameFromToken-Methode
Ruft den UTF-8-Namen des Objekts ab, auf das vom angegebenen Metadatentoken verwiesen wird. Diese Methode ist veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tk`  
 in Das Token, das das Objekt darstellt, für das der Name zurückgegeben wird.  
  
 `pszUtf8NamePtr`  
 vorgenommen Ein Zeiger auf den UTF-8-Objektnamen im Heap.  
  
## <a name="remarks"></a>Hinweise  
 `GetNameFromToken` ist veraltet. Als Alternative können Sie eine-Methode aufzurufen, um die Eigenschaften des jeweiligen Typs des erforderlichen Tokens abzurufen, z. b. `GetFieldProps` für ein Feld oder `GetMethodProps` für eine Methode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:** 1,0  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
