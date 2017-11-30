---
title: IMetaDataImport::EnumUnresolvedMethods-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumUnresolvedMethods
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3c7709180e5b7811379c25977f8a8d23b91adb3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumunresolvedmethods-method"></a>IMetaDataImport::EnumUnresolvedMethods-Methode
Zählt MemberDef-Token auf, die die nicht aufgelösten Methoden im aktuellen Metadatenbereich darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dies muss für den ersten Aufruf dieser Methode NULL sein.  
  
 `rMethods`  
 [out] Das Array zum Speichern der MemberDef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rMethods`-Arrays.  
  
 `pcTokens`  
 [out] Die Anzahl der zurückgegebenen MemberDef-Token `rMethods`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumUnresolvedMethods`wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Token aufgelistet werden. In diesem Fall `pcTokens` 0 (null).|  
  
## <a name="remarks"></a>Hinweise  
 Eine nicht aufgelöste Methode ist eine, die deklariert, aber nicht implementiert wurde. Eine Methode ist in der Enumeration enthalten, wenn die Methode gekennzeichnet ist `miForwardRef` und entweder `mdPinvokeImpl` oder `miRuntime` auf 0 (null) festgelegt ist. Das heißt, nicht aufgelöste Methode ist eine Methode einer Klasse, die markiert ist `miForwardRef` aber die nicht in nicht verwaltetem Code (über PInvoke erreicht) implementiert ist, oder intern von der Laufzeit selbst implementiert  
  
 Die Enumeration schließt alle Methoden, die im Modul Gültigkeitsbereich (Global) oder in Schnittstellen oder abstrakten Klassen definiert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
