---
title: IMetaDataTables::GetCodedTokenInfo-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
ms.openlocfilehash: b79ac7f71ec0551336298a90829e1f37e2e30b20
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711069"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a>IMetaDataTables::GetCodedTokenInfo-Methode

Ruft einen Zeiger auf ein Array von Token ab, die dem angegebenen Zeilen Index zugeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ixCdTkn`  
 in Die Art des zurück zugebende codierten Tokens.  
  
 `pcTokens`  
 vorgenommen Ein Zeiger auf die Länge von `ppTokens` .  
  
 `ppTokens`  
 vorgenommen Ein Zeiger auf einen Zeiger auf ein Array, das die Liste der zurückgegebenen Token enthält.  
  
 `ppName`  
 vorgenommen Ein Zeiger auf einen Zeiger auf den Namen des Tokens bei `ixCdTkn` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataTables-Schnittstelle](imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](imetadatatables2-interface.md)
