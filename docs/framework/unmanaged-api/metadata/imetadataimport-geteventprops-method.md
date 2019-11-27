---
title: IMetaDataImport::GetEventProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
ms.openlocfilehash: 18fe0c834506d0ac4cd15fd7af4c4f15904b0f81
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437585"
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps-Methode
Ruft Metadateninformationen für das Ereignis ab, das durch das angegebene Ereignis Token dargestellt wird, einschließlich des deklarierenden Typs, der Add-und Remove-Methoden für Delegaten sowie aller Flags und anderer zugeordneter Daten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,   
   [out] LPCWSTR       szEvent,   
   [in]  ULONG         cchEvent,   
   [out] ULONG         *pchEvent,   
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,   
   [out] mdMethodDef   *pmdRemoveOn,   
   [out] mdMethodDef   *pmdFire,   
   [out] mdMethodDef   rmdOtherMethod[],   
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ev`  
 in Das Ereignis Metadatentoken, das das Ereignis darstellt, für das Metadaten zu erhalten sind.  
  
 `pClass`  
 vorgenommen Ein Zeiger auf das TypeDef-Token, das die Klasse darstellt, die das Ereignis deklariert.  
  
 `szEvent`  
 vorgenommen Der Name des Ereignisses, auf das von `ev`verwiesen wird.  
  
 `pchEvent`  
 in Die angeforderte Länge in breit Zeichen `szEvent`.  
  
 `pdwEventFlags`  
 vorgenommen Die zurückgegebene Länge in breit Zeichen `szEvent`.  
  
 `ptkEventType`  
 vorgenommen Ein Zeiger auf ein TypeRef-oder TypeDef-Metadatentoken, das den <xref:System.Delegate> Typ des Ereignisses darstellt.  
  
 `pmdAddOn`  
 vorgenommen Ein Zeiger auf das Metadatentoken, das die Methode darstellt, mit der Handler für das Ereignis hinzugefügt werden.  
  
 `pmdRemoveOn`  
 vorgenommen Ein Zeiger auf das Metadatentoken, das die Methode darstellt, die Handler für das Ereignis entfernt.  
  
 `pmdFire`  
 vorgenommen Ein Zeiger auf das Metadatentoken, das die Methode darstellt, die das Ereignis auslöst.  
  
 `rmdOtherMethod`  
 vorgenommen Ein Array von Tokenzeigern auf andere Methoden, die dem Ereignis zugeordnet sind.  
  
 `cMax`  
 [in] Die maximale Größe des `rmdOtherMethod`-Arrays.  
  
 `pcOtherMethod`  
 vorgenommen Die Anzahl der in `rmdOtherMethod`zurückgegebenen Token.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
