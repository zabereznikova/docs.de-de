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
ms.openlocfilehash: e8d871f2ecbd96d5bda781b2ae11b94efd409442
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049920"
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
  
## <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `cl`  
 [in] Eine TypeDef-Token, das den Typ, dessen Member aufgelistet werden darstellt.  
  
 `rMembers`  
 [out] Das Array, die MemberDef-Token enthalten.  
  
 `cMax`  
 [in] Die maximale Größe des `rMembers`-Arrays.  
  
 `pcTokens`  
 [out] Die tatsächliche Anzahl der zurückgegebenen MemberDef-Token `rMembers`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es gibt keine MemberDef-Token, die aufgelistet werden. In diesem Fall `pcTokens` ist 0 (null).|  
  
## <a name="remarks"></a>Hinweise  
 Beim Auflisten von Sammlungen von Elementen für eine Klasse von `EnumMembers` gibt nur Mitglieder (Felder und Methoden, aber **nicht** Eigenschaften oder Ereignisse) direkt in der Klasse definiert. Es gibt keine Member, die die Klasse erbt, zurück, auch wenn die Klasse eine Implementierung für diese geerbten Member bereitstellt. Um geerbte Member aufzulisten, muss der Aufrufer explizit die Vererbungskette geführt. Beachten Sie, dass die Regeln für die Vererbungskette variieren abhängig von der Sprache und Compiler, die die ursprüngliche Metadaten ausgegeben.
 
 Eigenschaften und Ereignisse werden nicht durch den aufgezählt `EnumMembers`. Verwenden Sie zum Auflisten von den [EnumProperties](imetadataimport-enumproperties-method.md) oder [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
