---
title: IMetaDataTables::GetGuid-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type:
- apiref
ms.openlocfilehash: 57df124f15f78daad053d9634e1baa969a65cc35
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175277"
---
# <a name="imetadatatablesgetguid-method"></a>IMetaDataTables::GetGuid-Methode
Ruft eine GUID aus der Zeile am angegebenen Index ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetGuid (
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ixGuid`  
 [in] Der Index der Zeile, aus der die GUID abgesendet werden soll.  
  
 `ppGuid`  
 [out] Ein Zeiger auf einen Zeiger auf die GUID.  
  
## <a name="remarks"></a>Bemerkungen  

  Die Verwendung dieser Methode wird nicht empfohlen, da sie keine konsistenten Ergebnisse liefert. Informationen zur GUID-Tabelle finden Sie in der CLI-Dokumentation (Common Language Infrastructure), insbesondere "Partition II: Metadata Definition and Semantics". Die Dokumentation ist online verfügbar; siehe [ECMA-C- und Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) und Standard [ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataTables-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
