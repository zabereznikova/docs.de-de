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
ms.openlocfilehash: f20652a7f86576e64646a1f63c3e2c48b55cf811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175459"
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
 [in, out] Ein Zeiger auf den Enumerator. Dies muss NULL für den ersten Aufruf dieser Methode sein.  
  
 `mb`  
 [in] Ein MethodDef-Token, das den Umfang der Enumeration einschränkt.  
  
 `rEventProp`  
 [out] Das Array, das zum Speichern der Ereignisse oder Eigenschaften verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rEventProp`-Arrays.  
  
 `pcEventProp`  
 [out] Die Anzahl der Ereignisse `rEventProp`oder Eigenschaften, die in zurückgegeben werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics`erfolgreich zurückgegeben werden.|  
|`S_FALSE`|Es sind keine Ereignisse oder Eigenschaften zum Aufzählen vorhanden. In diesem `pcEventProp` Fall ist Null.|  
  
## <a name="remarks"></a>Bemerkungen  
 Viele Common Language-Laufzeittypen definieren `On` *Eigenschaftsereignisse* `Changed` und *Eigenschaftenmethoden,* `Changed` die sich auf ihre Eigenschaften beziehen. Der <xref:System.Windows.Forms.Control?displayProperty=nameWithType> Typ definiert beispielsweise <xref:System.Windows.Forms.Control.Font%2A> eine Eigenschaft, ein <xref:System.Windows.Forms.Control.FontChanged> <xref:System.Windows.Forms.Control.OnFontChanged%2A> Ereignis und eine Methode. Die set accessor-Methode <xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control.OnFontChanged%2A> der Eigenschaftsaufrufmethode, <xref:System.Windows.Forms.Control.FontChanged> die wiederum das Ereignis auslöst. Sie würden `EnumMethodSemantics` die Anwendung <xref:System.Windows.Forms.Control.OnFontChanged%2A> von MethodDef <xref:System.Windows.Forms.Control.Font%2A> aufrufen, <xref:System.Windows.Forms.Control.FontChanged> um Verweise auf die Eigenschaft und das Ereignis abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
