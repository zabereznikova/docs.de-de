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
ms.openlocfilehash: 92503df60ae44dfd44819fe3eda8e6a0549b2b66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720988"
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
 in Ein TypeDef-Token, das den Typ darstellt, dessen Member aufgelistet werden sollen.  
  
 `rMembers`  
 vorgenommen Das Array, das zum Speichern der mitgliedtendef-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rMembers`-Arrays.  
  
 `pcTokens`  
 vorgenommen Die tatsächliche Anzahl der in zurückgegebenen mitgliedsdef-Token `rMembers` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine mitgliedungstokentoken zum Auflisten vorhanden. In diesem Fall `pcTokens` ist 0 (null).|  
  
## <a name="remarks"></a>Hinweise  

 Beim Auflisten von Auflistungen von Membern für eine Klasse `EnumMembers` gibt nur Member (Felder und Methoden, aber **keine** Eigenschaften oder Ereignisse) zurück, die direkt in der Klasse definiert sind. Er gibt keine Member zurück, die die Klasse erbt, selbst wenn die Klasse eine Implementierung für diese geerbten Member bereitstellt. Um geerbte Member aufzuzählen, muss der Aufrufer die Vererbungs Kette explizit durchlaufen. Beachten Sie, dass die Regeln für die Vererbungs Kette abhängig von der Sprache oder dem Compiler variieren können, die die ursprünglichen Metadaten ausgegeben haben.

 Eigenschaften und Ereignisse werden nicht durch aufgezählt `EnumMembers` . Um diese aufzulisten, verwenden Sie [EnumProperties](imetadataimport-enumproperties-method.md) oder [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
