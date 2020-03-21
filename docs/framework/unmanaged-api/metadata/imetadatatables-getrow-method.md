---
title: IMetaDataTables::GetRow-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 71f6c496816fec1a7537f5ccdfdc1b47d17da871
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177106"
---
# <a name="imetadatatablesgetrow-method"></a>IMetaDataTables::GetRow-Methode
Ruft die Zeile am angegebenen Zeilenindex in der Tabelle am angegebenen Tabellenindex ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ixTbl`  
 [in] Der Index der Tabelle, aus der die Zeile abgerufen wird.  
  
 `rid`  
 [in] Der Index der zu erhaltenden Zeile.  
  
 `ppRow`  
 [out] Ein Zeiger auf einen Zeiger auf die Zeile.  
  
## <a name="remarks"></a>Bemerkungen  

  Die Verwendung dieser Methode wird nicht empfohlen, da sie keine konsistenten Ergebnisse liefert. Informationen zur GUID-Tabelle finden Sie in der CLI-Dokumentation (Common Language Infrastructure), insbesondere "Partition II: Metadata Definition and Semantics". Die Dokumentation ist online verfügbar; siehe [ECMA-C- und Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) und Standard [ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataTables-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
