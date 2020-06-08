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
ms.openlocfilehash: 7e60dd9535809ca13f3bbe6ac76f5ea1209df734
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501169"
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
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataTables-Schnittstelle](imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](imetadatatables2-interface.md)
