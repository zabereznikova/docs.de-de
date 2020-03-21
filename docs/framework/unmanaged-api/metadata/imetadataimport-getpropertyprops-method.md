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
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175329"
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
 [in] Ein Token, das die Eigenschaft darstellt, für die Metadaten zurückgegeben werden sollen.  
  
 `pClass`  
 [out] Ein Zeiger auf das TypeDef-Token, das den Typ darstellt, der die Eigenschaft implementiert.  
  
 `szProperty`  
 [out] Ein Puffer, der den Eigenschaftsnamen aufhält.  
  
 `cchProperty`  
 [in] Die Größe in `szProperty`breiten Zeichen von .  
  
 `pchProperty`  
 [out] Die Anzahl der in `szProperty`zurückgegebenen breiten Zeichen.  
  
 `pdwPropFlags`  
 [out] Ein Zeiger auf alle Attributflags, die auf die Eigenschaft angewendet werden. Dieser Wert ist eine Bitmaske aus der [CorPropertyAttr-Enumeration.](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)  
  
 `ppvSig`  
 [out] Ein Zeiger auf die Metadatensignatur der Eigenschaft.  
  
 `pbSig`  
 [out] Die Anzahl der `ppvSig`in zurückgegebenen Bytes.  
  
 `pdwCPlusTypeFlag`  
 [out] Ein Flag, das den Typ der Konstante angibt, die der Standardwert der Eigenschaft ist. Dieser Wert stammt aus der CorElementType-Enumeration.  
  
 `ppDefaultValue`  
 [out] Ein Zeiger auf die Bytes, die den Standardwert für diese Eigenschaft speichern.  
  
 `pcchDefaultValue`  
 [out] Die Größe in `ppDefaultValue`breiten `pdwCPlusTypeFlag` Zeichen von , wenn ELEMENT_TYPE_STRING ist; andernfalls ist dieser Wert nicht relevant. In diesem Fall wird `ppDefaultValue` die Länge von aus dem `pdwCPlusTypeFlag`Typ abgeleitet, der von angegeben wird.  
  
 `pmdSetter`  
 [out] Ein Zeiger auf das MethodDef-Token, das die Set-Accessor-Methode für die Eigenschaft darstellt.  
  
 `pmdGetter`  
 [out] Ein Zeiger auf das MethodDef-Token, das die get-Accessor-Methode für die Eigenschaft darstellt.  
  
 `rmdOtherMethod`  
 [out] Ein Array von MethodDef-Token, die andere Methoden darstellen, die der Eigenschaft zugeordnet sind.  
  
 `cMax`  
 [in] Die maximale Größe des `rmdOtherMethod`-Arrays. Wenn Sie kein Array bereitstellen, das groß genug ist, um alle Methoden zu halten, werden diese ohne Warnung übersprungen.  
  
 `pcOtherMethod`  
 [out] Die Anzahl der methodDef-Token, die in `rmdOtherMethod`zurückgegeben werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
