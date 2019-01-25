---
title: IMetaDataTables::GetTableInfo-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9bf3e5d427698673576f71e290fde54275b75317
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683455"
---
# <a name="imetadatatablesgettableinfo-method"></a>IMetaDataTables::GetTableInfo-Methode
Ruft ab, Name, Größe, Anzahl der Zeilen, die Anzahl der Spalten und Schlüsselspaltenindex der angegebenen Tabelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ixTbl`  
 [in] Der Bezeichner der Tabelle, deren Eigenschaften zurückgegeben.  
  
 `pcbRow`  
 [out] Ein Zeiger auf die Größe in Bytes, der eine Zeile einer Tabelle.  
  
 `pcRows`  
 [out] Ein Zeiger auf die Anzahl der Zeilen in der Tabelle.  
  
 `pcCols`  
 [out] Ein Zeiger auf die Anzahl der Spalten in der Tabelle.  
  
 `piKey`  
 [out] Ein Zeiger auf den Index der Spalte für den Schlüssel oder -1, wenn die Tabelle keine Schlüsselspalte.  
  
 `ppName`  
 [out] Ein Zeiger auf einen Zeiger auf den Namen der Tabelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataTables-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
