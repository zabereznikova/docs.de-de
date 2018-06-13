---
title: IMetaDataImport::EnumMembers-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 46ee8c62861a62ac044f295f7da082756d87347b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447632"
---
# <a name="imetadataimportenummembers-method"></a>IMetaDataImport::EnumMembers-Methode
Zählt MemberDef-Token auf, die Elemente des angegebenen Typs darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `cl`  
 [in] Eine TypeDef-Token, die den Typ, dessen Member aufzuzählenden darstellt.  
  
 `rMembers`  
 [out] Das Array zum Speichern der MemberDef-Token verwendet.  
  
 `cMax`  
 [in] Die maximale Größe des `rMembers`-Arrays.  
  
 `pcTokens`  
 [out] Die tatsächliche Anzahl von MemberDef-Token im zurückgegebenen `rMembers`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine MemberDef-Token, aufgelistet werden. In diesem Fall `pcTokens` 0 (null).|  
  
## <a name="remarks"></a>Hinweise  
 Beim Aufzählen von Auflistungen von Elementen für eine Klasse `EnumMembers` gibt nur Elemente, die direkt für die Klasse definiert. Es gibt keine Member, die die Klasse erbt, zurück, selbst wenn die Klasse eine Implementierung für diese geerbten Member bereitstellt. Um geerbte Member aufzulisten, muss der Aufrufer die Vererbungskette explizit durchlaufen. Beachten Sie, dass die Regeln für die Vererbungskette variiert je nach Sprache oder Compiler, die die ursprüngliche Metadaten ausgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
