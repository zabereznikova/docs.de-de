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
ms.openlocfilehash: acb772a64c8f13405f2836bb5f4f308986dce414
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447656"
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
 vorgenommen Die tatsächliche Anzahl der in `rMembers`zurückgegebenen mitgliedsdef-Token.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine mitgliedungstokentoken zum Auflisten vorhanden. In diesem Fall `pcTokens` gleich 0 (null) ist.|  
  
## <a name="remarks"></a>Hinweise  
 Beim Auflisten von Auflistungen von Membern für eine Klasse gibt `EnumMembers` nur Member (Felder und Methoden, aber **keine** Eigenschaften oder Ereignisse) zurück, die direkt in der Klasse definiert sind. Er gibt keine Member zurück, die die Klasse erbt, selbst wenn die Klasse eine Implementierung für diese geerbten Member bereitstellt. Um geerbte Member aufzuzählen, muss der Aufrufer die Vererbungs Kette explizit durchlaufen. Beachten Sie, dass die Regeln für die Vererbungs Kette abhängig von der Sprache oder dem Compiler variieren können, die die ursprünglichen Metadaten ausgegeben haben.
 
 Eigenschaften und Ereignisse werden nicht durch `EnumMembers`aufgezählt. Um diese aufzulisten, verwenden Sie [EnumProperties](imetadataimport-enumproperties-method.md) oder [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
