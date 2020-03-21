---
title: IMetaDataImport::EnumInterfaceImpls-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: b535fdd5027a26cc4dd0eafec9883f0186773dd1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175498"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>IMetaDataImport::EnumInterfaceImpls-Methode
Zählt alle Schnittstellen auf, die `TypeDef`von der angegebenen implementiert sind.
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `td`  
 [in] Das Token der TypeDef, deren MethodDef-Token, die Schnittstellenimplementierungen darstellen, aufgezählt werden sollen.  
  
 `rImpls`  
 [out] Das Array, das zum Speichern der MethodDef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Länge `rImpls` des Arrays.  
  
 `pcImpls`  
 [out] Die tatsächliche Anzahl der `rImpls`Token, die in zurückgegeben werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls`erfolgreich zurückgegeben werden.|  
|`S_FALSE`|Es sind keine MethodDef-Token zum Aufzählen vorhanden. In diesem `pcImpls` Fall ist auf Null gesetzt.|  

## <a name="remarks"></a>Bemerkungen

Die Enumeration gibt `mdInterfaceImpl` eine Auflistung von Token für `TypeDef`jede Schnittstelle zurück, die von der angegebenen implementiert ist. Schnittstellentoken werden in der Reihenfolge zurückgegeben, in `DefineTypeDef` `SetTypeDefProps`der die Schnittstellen angegeben wurden (durch oder ). Eigenschaften der `mdInterfaceImpl` zurückgegebenen Token können mit [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)abgefragt werden.
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
