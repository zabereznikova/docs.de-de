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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65bc4bc74e06368e6c7be9b742a8f311ecadc7fc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782319"
---
# <a name="imetadataimportgetmethodsemantics-method"></a>IMetaDataImport::GetMethodSemantics-Methode
Ruft Flags, die die Beziehung zwischen dem-Methode auf, die vom angegebenen MethodDef-Token und der gepaarten Eigenschaft verwiesen wird und ein Ereignis, die auf die verwiesen wird vom angegebenen EventProp-token ab.  
  
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
 [in] Ein MethodDef-Token, die die semantische Informationen für die abzurufenden Methode darstellt.  
  
 `tkEventProp`  
 [in] Ein Token, das darstellt, die gepaarten Eigenschaft und das Ereignis für den die Rolle der Methode abgerufen.  
  
 `pdwSemanticsFlags`  
 [out] Ein Zeiger auf die zugeordnete Semantik-Flags. Dieser Wert ist eine Bitmaske aus der [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) Enumeration.  
  
## <a name="remarks"></a>Hinweise  
 Die [IMetaDataEmit:: DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) Methode wird von einer Methode Semantikflags.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
