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
ms.openlocfilehash: 3d14aea92633c944d21d867c8152767ae6f1f291
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720970"
---
# <a name="imetadataimportenummethodsemantics-method"></a>IMetaDataImport::EnumMethodSemantics-Methode

Zählt die Eigenschaften und die Eigenschaftenänderungsereignisse auf, auf die sich die angegebene Methode bezieht.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.  
  
 `mb`  
 in Ein MethodDef-Token, das den Bereich der-Enumeration einschränkt.  
  
 `rEventProp`  
 vorgenommen Das Array, das zum Speichern der Ereignisse oder Eigenschaften verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rEventProp`-Arrays.  
  
 `pcEventProp`  
 vorgenommen Die Anzahl der in zurückgegebenen Ereignisse oder Eigenschaften `rEventProp` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Ereignisse oder Eigenschaften zum Auflisten vorhanden. In diesem Fall `pcEventProp` ist 0 (null).|  
  
## <a name="remarks"></a>Hinweise  

 Viele Common Language Runtime Typen definieren *Eigenschafts* `Changed` Ereignisse und `On` *Eigenschafts* `Changed` Methoden, die sich auf ihre Eigenschaften beziehen. Der <xref:System.Windows.Forms.Control?displayProperty=nameWithType> -Typ definiert z. b <xref:System.Windows.Forms.Control.Font%2A> . eine Eigenschaft, ein <xref:System.Windows.Forms.Control.FontChanged> -Ereignis und eine- <xref:System.Windows.Forms.Control.OnFontChanged%2A> Methode. Die Set-Accessor-Methode der- <xref:System.Windows.Forms.Control.Font%2A> Eigenschaft ruft die- <xref:System.Windows.Forms.Control.OnFontChanged%2A> Methode auf, die wiederum das- <xref:System.Windows.Forms.Control.FontChanged> Ereignis auslöst. Zum Abrufen von `EnumMethodSemantics` <xref:System.Windows.Forms.Control.OnFontChanged%2A> verweisen auf die <xref:System.Windows.Forms.Control.Font%2A> -Eigenschaft und das-Ereignis wird die Verwendung von MethodDef für aufgerufen <xref:System.Windows.Forms.Control.FontChanged> .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
