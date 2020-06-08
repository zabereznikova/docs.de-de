---
title: IMetaDataImport::GetTypeRefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
ms.openlocfilehash: 273922e00c3e5319d5a03652cc77b69f4479ea67
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503522"
---
# <a name="imetadataimportgettyperefprops-method"></a>IMetaDataImport::GetTypeRefProps-Methode
Ruft die Metadaten ab, die dem zugeordnet sind, <xref:System.Type> auf die vom angegebenen TypeRef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tr`  
 in Das TypeRef-Token, das den Typ darstellt, für den Metadaten zurückgegeben werden sollen.  
  
 `ptkResolutionScope`  
 vorgenommen Ein Zeiger auf den Bereich, in dem der Verweis erfolgt. Dieser Wert ist ein AssemblyRef-oder ModuleRef-Token.  
  
 `szName`  
 vorgenommen Ein Puffer, der den Typnamen enthält.  
  
 `cchName`  
 in Die angeforderte Größe in breit Zeichen von `szName` .  
  
 `pchName`  
 vorgenommen Die zurückgegebene Größe in breit Zeichen von `szName` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
