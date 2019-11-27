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
ms.openlocfilehash: ff6932b6040a19e0ccda2f8d2140fa131cdd9224
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450080"
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
 vorgenommen Die Anzahl der Ereignisse oder Eigenschaften, die in `rEventProp`zurückgegeben werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Ereignisse oder Eigenschaften zum Auflisten vorhanden. In diesem Fall `pcEventProp` gleich 0 (null) ist.|  
  
## <a name="remarks"></a>Hinweise  
 Viele Common Language Runtime *Typen definieren Eigenschaften*`Changed` Ereignisse *und `On`Eigenschaften*`Changed` Methoden, die mit ihren Eigenschaften verknüpft sind. Der <xref:System.Windows.Forms.Control?displayProperty=nameWithType>-Typ definiert z. b. eine <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft, ein <xref:System.Windows.Forms.Control.FontChanged>-Ereignis und eine <xref:System.Windows.Forms.Control.OnFontChanged%2A>-Methode. Die Set-Accessor-Methode der <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft ruft <xref:System.Windows.Forms.Control.OnFontChanged%2A>-Methode auf, die wiederum das <xref:System.Windows.Forms.Control.FontChanged>-Ereignis auslöst. Zum Abrufen von Verweisen auf die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft und das <xref:System.Windows.Forms.Control.FontChanged> Ereignis würden Sie `EnumMethodSemantics` mithilfe der Method<xref:System.Windows.Forms.Control.OnFontChanged%2A> DEF-Methode abrufen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
