---
title: IMetaDataImport::EnumMembersWithName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
ms.openlocfilehash: 35b82c33e54619eb9bebd5e5749ae202e905357a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720989"
---
# <a name="imetadataimportenummemberswithname-method"></a>IMetaDataImport::EnumMembersWithName-Methode

Zählt MemberDef-Token auf, die Elemente des angegebenen Typs mit dem angegebenen Namen darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [in]      LPCWSTR     szName,
   [out]     mdToken     rMembers[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator.  
  
 `cl`  
 in Ein TypeDef-Token, das den Typ mit aufzuzählenden Membern darstellt.  
  
 `szName`  
 in Der Elementname, der den Bereich des Enumerators einschränkt.  
  
 `rMembers`  
 vorgenommen Das Array, das zum Speichern der mitgliedungstokentoken verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rMembers`-Arrays.  
  
 `pcTokens`  
 vorgenommen Die tatsächliche Anzahl der in zurückgegebenen mitgliedsdef-Token `rMembers` .  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode listet Felder und Methoden auf, aber keine Eigenschaften oder Ereignisse. Im Gegensatz zu [IMetaDataImport:: EnumMembers](imetadataimport-enummembers-method.md) `EnumMembersWithName` verwirft alle Feld-und Element Token, die nicht über den angegebenen Namen verfügen.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine mitgliedungstokentoken zum Auflisten vorhanden. In diesem Fall `pcTokens` ist 0 (null).|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
