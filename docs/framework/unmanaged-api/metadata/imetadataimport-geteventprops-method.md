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
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177273"
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps-Methode
Ruft Metadateninformationen für das Ereignis ab, das durch das angegebene Ereignistoken dargestellt wird, einschließlich des deklarierenden Typs, der Add- und Remove-Methoden für Delegaten sowie aller Flags und anderer zugeordneter Daten.  
  
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
 [in] Das Ereignismetadatentoken, das das Ereignis darstellt, für das Metadaten abgerufen werden sollen.  
  
 `pClass`  
 [out] Ein Zeiger auf das TypeDef-Token, das die Klasse darstellt, die das Ereignis deklariert.  
  
 `szEvent`  
 [out] Der Name des Ereignisses, auf das von `ev`verwiesen wird.  
  
 `pchEvent`  
 [in] Die angeforderte Länge `szEvent`in breiten Zeichen von .  
  
 `pdwEventFlags`  
 [out] Die zurückgegebene Länge `szEvent`in breiten Zeichen von .  
  
 `ptkEventType`  
 [out] Ein Zeiger auf ein TypeRef- oder <xref:System.Delegate> TypeDef-Metadatentoken, das den Typ des Ereignisses darstellt.  
  
 `pmdAddOn`  
 [out] Ein Zeiger auf das Metadatentoken, das die Methode darstellt, die Handler für das Ereignis hinzufügt.  
  
 `pmdRemoveOn`  
 [out] Ein Zeiger auf das Metadatentoken, das die Methode darstellt, die Handler für das Ereignis entfernt.  
  
 `pmdFire`  
 [out] Ein Zeiger auf das Metadatentoken, das die Methode darstellt, die das Ereignis auslöst.  
  
 `rmdOtherMethod`  
 [out] Ein Array von Tokenzeigern auf andere Methoden, die dem Ereignis zugeordnet sind.  
  
 `cMax`  
 [in] Die maximale Größe des `rmdOtherMethod`-Arrays.  
  
 `pcOtherMethod`  
 [out] Die Anzahl der Token, die in `rmdOtherMethod`zurückgegeben werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
