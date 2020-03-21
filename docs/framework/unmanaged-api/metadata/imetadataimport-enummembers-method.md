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
ms.openlocfilehash: 20c7a90f27defa18a5ef311d1f3a549b81fc5c40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175485"
---
# <a name="imetadataimportenummembers-method"></a>IMetaDataImport::EnumMembers-Methode
Zählt MemberDef-Token auf, die Elemente des angegebenen Typs darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 [in] Ein TypeDef-Token, das den Typ darstellt, dessen Member aufgezählt werden sollen.  
  
 `rMembers`  
 [out] Das Array, das zum Besitz der MemberDef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rMembers`-Arrays.  
  
 `pcTokens`  
 [out] Die tatsächliche Anzahl der MemberDef-Token, die in `rMembers`zurückgegeben wurden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers`erfolgreich zurückgegeben werden.|  
|`S_FALSE`|Es sind keine MemberDef-Token zum Aufzählen vorhanden. In diesem `pcTokens` Fall ist Null.|  
  
## <a name="remarks"></a>Bemerkungen  
 Beim Aufzählen von Auflistungen von `EnumMembers` Membern für eine Klasse werden nur Member zurückgegeben (Felder und Methoden, jedoch **keine** Eigenschaften oder Ereignisse), die direkt für die Klasse definiert sind. Es werden keine Member zurückgegeben, die von der Klasse geerbt werden, auch wenn die Klasse eine Implementierung für diese geerbten Member bereitstellt. Um geerbte Member aufzuzählen, muss der Aufrufer die Vererbungskette explizit aufrufen. Beachten Sie, dass die Regeln für die Vererbungskette je nach Sprache oder Compiler, der die ursprünglichen Metadaten ausgegeben hat, variieren können.

 Eigenschaften und Ereignisse werden nicht `EnumMembers`von aufgezählt. Um diese aufzuzählen, verwenden Sie [EnumProperties](imetadataimport-enumproperties-method.md) oder [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
