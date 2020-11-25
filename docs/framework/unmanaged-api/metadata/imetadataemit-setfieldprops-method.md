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
ms.openlocfilehash: 0f98fb64b43822c437c39df2f3c51a222ef386b9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730395"
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
 in Der `ELEMENT_TYPE_` *\** für den konstanten Wert. Dies ist ein- `CorElementType` Wert. Wenn keine Konstante definiert ist, legen Sie diesen Wert auf fest `ELEMENT_TYPE_END` .  
  
 `pValue`  
 in Der Konstante Wert für das Feld.  
  
 `cchValue`  
 in Die Größe von in Unicode-Zeichen `pValue` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
