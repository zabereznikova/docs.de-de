---
title: IMetaDataEmit::SetFieldProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: efc627619d9abf9cfa6010e1c0ca709989b9cad3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445462"
---
# <a name="imetadataemitsetfieldprops-method"></a>IMetaDataEmit::SetFieldProps-Methode
Legt den Standardwert für das Feld fest, auf das durch das angegebene Feld Token verwiesen wird, oder aktualisiert dieses.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `fd`  
 in Das Token für das Zielfeld.  
  
 `dwFieldFlags`  
 in Feld Attribute. Dies ist eine Bitmaske von `CorFieldAttr` Werten.  
  
 `dwCPlusTypeFlag`  
 in Der `ELEMENT_TYPE_` *\** für den konstanten Wert. Dies ist ein `CorElementType` Wert. Wenn keine Konstante definiert ist, legen Sie diesen Wert auf `ELEMENT_TYPE_END`fest.  
  
 `pValue`  
 in Der Konstante Wert für das Feld.  
  
 `cchValue`  
 in Die Größe `pValue`in Unicode-Zeichen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
