---
title: IMetaDataImport::GetMemberRefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: 3237b67f8f711e9ef213d6fc66f1513c534fbdeb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733203"
---
# <a name="imetadataimportgetmemberrefprops-method"></a>IMetaDataImport::GetMemberRefProps-Methode

Ruft Metadaten ab, die dem Element zugeordnet sind, auf das durch das angegebene Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,
   [out] mdToken           *ptk,
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pbSig
);  
```  
  
## <a name="parameters"></a>Parameter  

 `mr`  
 in Das Element, für das die zugeordneten Metadaten zurückgegeben werden sollen.  
  
 `ptk`  
 vorgenommen Ein TypeDef-oder TypeRef-oder TypeSpec-Token, das die Klasse darstellt, die den Member deklariert, oder ein ModuleRef-Token, das die Modul Klasse darstellt, die den Member deklariert, oder ein MethodDef-Token, das den Member darstellt.  
  
 `szMember`  
 vorgenommen Ein Zeichen folgen Puffer für den Namen des Members.  
  
 `cchMember`  
 in Die angeforderte Größe in breit Zeichen von `szMember` .  
  
 `pchMember`  
 vorgenommen Die zurückgegebene Größe in breit Zeichen von `szMember` .  
  
 `ppvSibBlob`  
 vorgenommen Ein Zeiger auf die binäre Metadatensignatur für den Member.  
  
 `pbSig`  
 vorgenommen Die Größe von in Bytes `ppvSigBlob` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
