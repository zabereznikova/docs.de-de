---
title: IMetaDataImport::GetPropertyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
ms.openlocfilehash: aded23e190de18d76bb2b9e2ffbae51cf2325419
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729225"
---
# <a name="imetadataimportgetpropertyprops-method"></a>IMetaDataImport::GetPropertyProps-Methode

Ruft die Metadaten für die Eigenschaft ab, die durch das angegebene Token dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,
   [out] LPCWSTR           szProperty,
   [in]  ULONG             cchProperty,
   [out] ULONG             *pchProperty,
   [out] DWORD             *pdwPropFlags,
   [out] PCCOR_SIGNATURE   *ppvSig,
   [out] ULONG             *pbSig,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,
   [out] mdMethodDef       *pmdGetter,
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,
   [out] ULONG             *pcOtherMethod
);  
```  
  
## <a name="parameters"></a>Parameter  

 `prop`  
 in Ein Token, das die Eigenschaft darstellt, für die Metadaten zurückgegeben werden sollen.  
  
 `pClass`  
 vorgenommen Ein Zeiger auf das TypeDef-Token, das den Typ darstellt, der die Eigenschaft implementiert.  
  
 `szProperty`  
 vorgenommen Ein Puffer, der den Eigenschaftsnamen enthalten soll.  
  
 `cchProperty`  
 in Die Größe in breit Zeichen von `szProperty` .  
  
 `pchProperty`  
 vorgenommen Die Anzahl der breit Zeichen, die in zurückgegeben werden `szProperty` .  
  
 `pdwPropFlags`  
 vorgenommen Ein Zeiger auf alle Attributflags, die auf die-Eigenschaft angewendet werden. Dieser Wert ist eine Bitmaske aus der [CorPropertyAttr](corpropertyattr-enumeration.md) -Enumeration.  
  
 `ppvSig`  
 vorgenommen Ein Zeiger auf die Metadatensignatur der Eigenschaft.  
  
 `pbSig`  
 vorgenommen Die Anzahl von Bytes, die in zurückgegeben werden `ppvSig` .  
  
 `pdwCPlusTypeFlag`  
 vorgenommen Ein Flag, das den Typ der Konstante angibt, die der Standardwert der Eigenschaft ist. Dieser Wert wird aus der CorElementType-Enumeration abgeleitet.  
  
 `ppDefaultValue`  
 vorgenommen Ein Zeiger auf die Bytes, in denen der Standardwert für diese Eigenschaft gespeichert wird.  
  
 `pcchDefaultValue`  
 vorgenommen Die Größe in breit Zeichen von `ppDefaultValue` , wenn `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING ist. andernfalls ist dieser Wert nicht relevant. In diesem Fall wird die Länge von `ppDefaultValue` von dem Typ abgeleitet, der durch angegeben wird `pdwCPlusTypeFlag` .  
  
 `pmdSetter`  
 vorgenommen Ein Zeiger auf das MethodDef-Token, das die Set-Accessor-Methode für die-Eigenschaft darstellt.  
  
 `pmdGetter`  
 vorgenommen Ein Zeiger auf das MethodDef-Token, das die Get-Accessor-Methode für die-Eigenschaft darstellt.  
  
 `rmdOtherMethod`  
 vorgenommen Ein Array von MethodDef-Token, die andere Methoden darstellen, die der-Eigenschaft zugeordnet sind.  
  
 `cMax`  
 [in] Die maximale Größe des `rmdOtherMethod`-Arrays. Wenn Sie kein Array bereitstellen, das groß genug ist, um alle Methoden aufzunehmen, werden diese ohne Warnung übersprungen.  
  
 `pcOtherMethod`  
 vorgenommen Die Anzahl der MethodDef-Token, die in zurückgegeben werden `rmdOtherMethod` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
