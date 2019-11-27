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
ms.openlocfilehash: 247a2793bf3806f5ee38585d50b4535820dfcb69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437057"
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
 in Die Größe in breit Zeichen `szProperty`.  
  
 `pchProperty`  
 vorgenommen Die Anzahl der breit Zeichen, die in `szProperty`zurückgegeben werden.  
  
 `pdwPropFlags`  
 vorgenommen Ein Zeiger auf alle Attributflags, die auf die-Eigenschaft angewendet werden. Dieser Wert ist eine Bitmaske aus der [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) -Enumeration.  
  
 `ppvSig`  
 vorgenommen Ein Zeiger auf die Metadatensignatur der Eigenschaft.  
  
 `pbSig`  
 vorgenommen Die Anzahl von Bytes, die in `ppvSig`zurückgegeben werden.  
  
 `pdwCPlusTypeFlag`  
 vorgenommen Ein Flag, das den Typ der Konstante angibt, die der Standardwert der Eigenschaft ist. Dieser Wert wird aus der CorElementType-Enumeration abgeleitet.  
  
 `ppDefaultValue`  
 vorgenommen Ein Zeiger auf die Bytes, in denen der Standardwert für diese Eigenschaft gespeichert wird.  
  
 `pcchDefaultValue`  
 vorgenommen Die Größe in breit Zeichen `ppDefaultValue`, wenn `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING ist. Andernfalls ist dieser Wert nicht relevant. In diesem Fall wird die Länge `ppDefaultValue` von dem Typ abgeleitet, der durch `pdwCPlusTypeFlag`angegeben wird.  
  
 `pmdSetter`  
 vorgenommen Ein Zeiger auf das MethodDef-Token, das die Set-Accessor-Methode für die-Eigenschaft darstellt.  
  
 `pmdGetter`  
 vorgenommen Ein Zeiger auf das MethodDef-Token, das die Get-Accessor-Methode für die-Eigenschaft darstellt.  
  
 `rmdOtherMethod`  
 vorgenommen Ein Array von MethodDef-Token, die andere Methoden darstellen, die der-Eigenschaft zugeordnet sind.  
  
 `cMax`  
 [in] Die maximale Größe des `rmdOtherMethod`-Arrays. Wenn Sie kein Array bereitstellen, das groß genug ist, um alle Methoden aufzunehmen, werden diese ohne Warnung übersprungen.  
  
 `pcOtherMethod`  
 vorgenommen Die Anzahl der MethodDef-Token, die in `rmdOtherMethod`zurückgegeben werden.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
