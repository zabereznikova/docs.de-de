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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e1b065ecb9a715601e617e288c1dfc0de8dd323d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466569"
---
# <a name="imetadataimportgetpropertyprops-method"></a>IMetaDataImport::GetPropertyProps-Methode
Ruft die Metadaten für die Eigenschaft, die durch das angegebene Token dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Ein Token, die die Metadaten für die zurückzugebende Eigenschaft darstellt.  
  
 `pClass`  
 [out] Ein Zeiger auf das TypeDef-Token, das den Typ darstellt, der der Eigenschaft implementiert.  
  
 `szProperty`  
 [out] Ein Puffer, die Namen der Eigenschaft enthalten soll.  
  
 `cchProperty`  
 [in] Die Größe in Breitzeichen `szProperty`.  
  
 `pchProperty`  
 [out] Die Anzahl der Breitzeichen, die in zurückgegebenen `szProperty`.  
  
 `pdwPropFlags`  
 [out] Ein Zeiger auf Attributflags auf die Eigenschaft angewendet werden soll. Dieser Wert ist eine Bitmaske aus der [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) Enumeration.  
  
 `ppvSig`  
 [out] Ein Zeiger auf die Signatur für die Metadaten der Eigenschaft.  
  
 `pbSig`  
 [out] Die Anzahl der Bytes, die in zurückgegebenen `ppvSig`.  
  
 `pdwCPlusTypeFlag`  
 [out] Ein Flag, das den Typ der Konstante, die der Standardwert der Eigenschaft angibt. Dieser Wert liegt zwischen CorElementType-Enumeration.  
  
 `ppDefaultValue`  
 [out] Ein Zeiger auf die Bytes, die der Standardwert für diese Eigenschaft zu speichern.  
  
 `pcchDefaultValue`  
 [out] Die Größe in Breitzeichen `ppDefaultValue`, wenn `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING ist; andernfalls ist dieser Wert nicht relevant. In diesem Fall die Länge des `ppDefaultValue` wird aus der vom angegebenen Typ abgeleitet, `pdwCPlusTypeFlag`.  
  
 `pmdSetter`  
 [out] Ein Zeiger auf das MethodDef-Token, das die Set-Accessor-Methode für die Eigenschaft darstellt.  
  
 `pmdGetter`  
 [out] Ein Zeiger auf das MethodDef-Token, das die Get-Accessor-Methode für die Eigenschaft darstellt.  
  
 `rmdOtherMethod`  
 [out] Ein Array von MethodDef-Token, die andere Methoden, die mit der Eigenschaft verknüpften darstellen.  
  
 `cMax`  
 [in] Die maximale Größe des `rmdOtherMethod`-Arrays. Wenn Sie ein Array, das groß genug für alle Methoden nicht angeben, werden sie ohne Warnung übersprungen.  
  
 `pcOtherMethod`  
 [out] Die Anzahl der zurückgegebenen MethodDef-Token `rmdOtherMethod`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
