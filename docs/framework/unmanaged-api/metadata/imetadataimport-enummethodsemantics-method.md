---
title: IMetaDataImport::EnumMethodSemantics-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3c20e2787eb8071b10e06b980572c347959fe3c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619447"
---
# <a name="imetadataimportenummethodsemantics-method"></a>IMetaDataImport::EnumMethodSemantics-Methode
Zählt die Eigenschaften und die Eigenschaftenänderungsereignisse auf, auf die sich die angegebene Methode bezieht.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dies muss NULL sein, für den ersten Aufruf dieser Methode.  
  
 `mb`  
 [in] Ein MethodDef-Token, das den Bereich der Enumeration einschränkt.  
  
 `rEventProp`  
 [out] Das Array zum Speichern von Ereignissen oder Eigenschaften verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rEventProp`-Arrays.  
  
 `pcEventProp`  
 [out] Die Anzahl von Ereignissen oder Eigenschaften, die in zurückgegebenen `rEventProp`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es gibt keine Ereignisse oder Eigenschaften aufgelistet werden. In diesem Fall `pcEventProp` ist 0 (null).|  
  
## <a name="remarks"></a>Hinweise  
 Viele Typen der common Language Runtime definieren *Eigenschaft* `Changed` Ereignisse und `On` *Eigenschaft* `Changed` Methoden, die sich auf ihre Eigenschaften. Z. B. die <xref:System.Windows.Forms.Control?displayProperty=nameWithType> Typ definiert ein <xref:System.Windows.Forms.Control.Font%2A> -Eigenschaft, ein <xref:System.Windows.Forms.Control.FontChanged> Ereignis und einem <xref:System.Windows.Forms.Control.OnFontChanged%2A> Methode. Die Set-Accessor-Methode, der die <xref:System.Windows.Forms.Control.Font%2A> eigenschaftsaufrufen <xref:System.Windows.Forms.Control.OnFontChanged%2A> -Methode, die wiederum löst die <xref:System.Windows.Forms.Control.FontChanged> Ereignis. Rufen Sie `EnumMethodSemantics` mithilfe von MethodDef für <xref:System.Windows.Forms.Control.OnFontChanged%2A> zum Abrufen von Verweisen auf die <xref:System.Windows.Forms.Control.Font%2A> Eigenschaft und die <xref:System.Windows.Forms.Control.FontChanged> Ereignis.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
