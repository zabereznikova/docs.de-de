---
title: IMetaDataImport::GetPropertyProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d838f43b500ac3dd0c3b44d9d84dd9fc039c6e16
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parameter  
 `prop`  
 [in] Ein Token, die die Metadaten für die zurückzugebende Eigenschaft darstellt.  
  
 `pClass`  
 [out] Ein Zeiger auf das TypeDef-Token, das den Typ darstellt, der die Eigenschaft implementiert.  
  
 `szProperty`  
 [out] Ein Puffer, der den Eigenschaftennamen enthält.  
  
 `cchProperty`  
 [in] Die Größe in Breitzeichen `szProperty`.  
  
 `pchProperty`  
 [out] Die Anzahl der Breitzeichen, die im zurückgegebenen `szProperty`.  
  
 `pdwPropFlags`  
 [out] Ein Zeiger auf Attributflags, die auf die Eigenschaft angewendet. Dieser Wert ist eine Bitmaske aus der [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) Enumeration.  
  
 `ppvSig`  
 [out] Ein Zeiger auf die Metadatensignatur der Eigenschaft.  
  
 `pbSig`  
 [out] Die Anzahl der Bytes im zurückgegebenen `ppvSig`.  
  
 `pdwCPlusTypeFlag`  
 [out] Ein Flag, das den Typ der Konstante, die der Standardwert der Eigenschaft angeben. Dieser Wert liegt zwischen CorElementType-Enumeration.  
  
 `ppDefaultValue`  
 [out] Ein Zeiger auf die Bytes, die den Standardwert für diese Eigenschaft zu speichern.  
  
 `pcchDefaultValue`  
 [out] Die Größe in Breitzeichen `ppDefaultValue`, wenn `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING ist; dieser Wert ist, andernfalls nicht relevant. In diesem Fall wird die Länge des `ppDefaultValue` wird aus der vom angegebenen Typ abgeleitet, `pdwCPlusTypeFlag`.  
  
 `pmdSetter`  
 [out] Ein Zeiger auf das MethodDef-Token, das die Set-Zugriffsmethode für die Eigenschaft darstellt.  
  
 `pmdGetter`  
 [out] Ein Zeiger auf das MethodDef-Token, das die Get-Accessor-Methode für die Eigenschaft darstellt.  
  
 `rmdOtherMethod`  
 [out] Ein Array von MethodDef-Token, die andere Methoden, die mit der Eigenschaft verknüpften darstellen.  
  
 `cMax`  
 [in] Die maximale Größe des `rmdOtherMethod`-Arrays. Wenn Sie ein Array, das groß genug für alle Methoden nicht angeben, werden sie ohne Warnung übersprungen.  
  
 `pcOtherMethod`  
 [out] Die Anzahl der zurückgegebenen MethodDef-Token `rmdOtherMethod`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
