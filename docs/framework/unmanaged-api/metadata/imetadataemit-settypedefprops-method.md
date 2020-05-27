---
title: IMetaDataEmit::SetTypeDefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: b05527f118de059c674ea659b1a22b7895126cf4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007766"
---
# <a name="imetadataemitsettypedefprops-method"></a>IMetaDataEmit::SetTypeDefProps-Methode
Legt Funktionen eines Typs fest, der durch einen vorherigen [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md)definiert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 in Ein `mdTypeDef` Token, das vom ursprünglichen-Befehl an [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md)abgerufen wurde.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` legt. Dies ist eine Bitmaske von `CorTypeAttr` Werten.  
  
 `tkExtends`  
 in Der der `mdToken` Basisklasse. Abgerufen von einem vorherigen-Befehl an [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md)oder `null` .  
  
 `rtkImplements[]`  
 in Ein Array von Token für die Schnittstellen, die von diesem Typ implementiert werden. Diese `mdTypeRef` Token werden mithilfe von [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md)abgerufen. Das letzte Element des Arrays muss sein `mdTokenNil` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
