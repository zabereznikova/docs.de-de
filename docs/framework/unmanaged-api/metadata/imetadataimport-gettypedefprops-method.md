---
title: IMetaDataImport::GetTypeDefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
ms.openlocfilehash: 6346b1e34e508e5c173bfd0119ac7451d7eef40e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490795"
---
# <a name="imetadataimportgettypedefprops-method"></a>IMetaDataImport::GetTypeDefProps-Methode
Gibt Metadateninformationen für das zurück, das <xref:System.Type> durch das angegebene TypeDef-Token dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 in Das TypeDef-Token, das den Typ darstellt, für den Metadaten zurückgegeben werden sollen.  
  
 `szTypeDef`  
 vorgenommen Ein Puffer, der den Typnamen enthält.  
  
 `cchTypeDef`  
 in Die Größe in breit Zeichen von `szTypeDef` .  
  
 `pchTypeDef`  
 vorgenommen Die Anzahl der breit Zeichen, die in zurückgegeben werden `szTypeDef` .  
  
 `pdwTypeDefFlags`  
 vorgenommen Ein Zeiger auf alle Flags, die die Typdefinition ändern. Dieser Wert ist eine Bitmaske aus der [CorTypeAttr](cortypeattr-enumeration.md) -Enumeration.  
  
 `ptkExtends`  
 vorgenommen Ein TypeDef-oder TypeRef-Metadatentoken, das den Basistyp des angeforderten Typs darstellt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
