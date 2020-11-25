---
title: IMetaDataImport::GetMethodSemantics-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: cc01a417c3246ad2554c506f21e37a3cbbdeb991
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733184"
---
# <a name="imetadataimportgetmethodsemantics-method"></a>IMetaDataImport::GetMethodSemantics-Methode

Ruft Flags ab, die die Beziehung zwischen der Methode angeben, auf die vom angegebenen MethodDef-Token verwiesen wird, und der gekoppelten Eigenschaft und dem Ereignis, auf die vom angegebenen EventProp  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `mb`  
 in Ein MethodDef-Token, das die Methode darstellt, für die die semantischen Rollen Informationen zu erhalten sind.  
  
 `tkEventProp`  
 in Ein Token, das die gekoppelte Eigenschaft und das Ereignis darstellt, für das die Rolle der Methode angezeigt werden soll.  
  
 `pdwSemanticsFlags`  
 vorgenommen Ein Zeiger auf die zugeordneten Semantik Flags. Dieser Wert ist eine Bitmaske aus der [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) -Enumeration.  
  
## <a name="remarks"></a>Hinweise  

 Mit der [IMetaDataEmit::D efineproperty](imetadataemit-defineproperty-method.md) -Methode werden die Semantik Flags einer Methode festgelegt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
