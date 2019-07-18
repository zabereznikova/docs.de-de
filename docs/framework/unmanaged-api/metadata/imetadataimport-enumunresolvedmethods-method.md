---
title: IMetaDataImport::EnumUnresolvedMethods-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74d0c2e9777a7bd3d49622fb326ecb6b58fbec07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782547"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a>IMetaDataImport::EnumUnresolvedMethods-Methode
Zählt MemberDef-Token auf, die die nicht aufgelösten Methoden im aktuellen Metadatenbereich darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dies muss NULL sein, für den ersten Aufruf dieser Methode.  
  
 `rMethods`  
 [out] Das Array zum Speichern der MemberDef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rMethods`-Arrays.  
  
 `pcTokens`  
 [out] Die Anzahl der zurückgegebenen MemberDef-Token `rMethods`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumUnresolvedMethods` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es gibt keine Token aufgelistet werden. In diesem Fall `pcTokens` ist 0 (null).|  
  
## <a name="remarks"></a>Hinweise  
 Eine nicht aufgelöste Methode ist, der deklariert, aber nicht implementiert wurde. Eine Methode ist in der Enumeration enthalten, wenn die Methode markiert ist `miForwardRef` und entweder `mdPinvokeImpl` oder `miRuntime` auf 0 (null) festgelegt ist. Das heißt, eine nicht aufgelöste Methode ist die Methode einer Klasse, die markiert ist `miForwardRef` , aber das ist nicht implementiert, die in nicht verwaltetem Code (über PInvoke erreicht) oder intern von der Laufzeit selbst implementiert  
  
 Die Enumeration schließt alle Methoden, die entweder im Modulbereich (Global) oder in Schnittstellen oder abstrakten Klassen definiert sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
