---
title: IMetaDataTables::GetString-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c2c0df58d1de7cc7c1eedfdea6c0e698cbd9cb48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetstring-method"></a>IMetaDataTables::GetString-Methode
Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte im aktuellen Verweisbereich.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ixString`  
 [in] Der Index, an dem beginnen, für den nächsten Wert gesucht werden soll.  
  
 `ppString`  
 [out] Ein Zeiger auf einen Zeiger auf den Wert der zurückgegebenen Zeichenfolge.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataTables-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
