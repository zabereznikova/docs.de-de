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
ms.openlocfilehash: 662b628f3cc6d2d7138f56820beaccee9c5d9e81
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426655"
---
# <a name="imetadatatablesgettableinfo-method"></a>IMetaDataTables::GetTableInfo-Methode
Ruft den Namen, die Zeilengröße, die Anzahl der Zeilen, die Anzahl der Spalten und den Schlüssel Spalten Index der angegebenen Tabelle ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ixTbl`  
 in Der Bezeichner der Tabelle, deren Eigenschaften zurückgegeben werden sollen.  
  
 `pcbRow`  
 vorgenommen Ein Zeiger auf die Größe einer Tabellenzeile in Byte.  
  
 `pcRows`  
 vorgenommen Ein Zeiger auf die Anzahl der Zeilen in der Tabelle.  
  
 `pcCols`  
 vorgenommen Ein Zeiger auf die Anzahl der Spalten in der Tabelle.  
  
 `piKey`  
 vorgenommen Ein Zeiger auf den Index der Schlüssel Spalte oder-1, wenn die Tabelle keine Schlüssel Spalte enthält.  
  
 `ppName`  
 vorgenommen Ein Zeiger auf einen Zeiger auf den Tabellennamen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataTables-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
