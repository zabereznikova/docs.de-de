---
title: IMetaDataTables::GetColumn-Methode
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: 270546f0270521e38cfdcae5e4d2137202c13cb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711070"
---
# <a name="imetadatatablesgetcolumn-method"></a>IMetaDataTables::GetColumn-Methode

Ruft einen Zeiger auf den Wert ab, der in der Zelle der angegebenen Spalte und Zeile in der angegebenen Tabelle enthalten ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a>Parameter

 `ixTbl`  
 in Der Index der Tabelle.  
  
 `ixCol`  
 in Der Index der Spalte in der Tabelle.  
  
 `rid`  
 in Der Index der Zeile in der Tabelle.  
  
 `pVal`  
 vorgenommen Ein Zeiger auf den Wert in der Zelle.  

## <a name="remarks"></a>Hinweise

Die Interpretation des Werts, der durch zurückgegeben wird, `pVal` hängt vom Typ der Spalte ab. Der Spaltentyp kann durch Aufrufen von [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md)bestimmt werden.

- Die **GetColumn** -Methode konvertiert Spalten vom Typ **RID** oder **codedtoken** automatisch in vollständige 32-Bit- `mdToken` Werte.
- Außerdem werden 8-Bit-oder 16-Bit-Werte automatisch in vollständige 32-Bit-Werte konvertiert.
- Bei *Heap* -Typspalten ist das zurückgegebene *PVal* ein Index in den entsprechenden Heap.

| Spaltentyp              | PVAL enthält | Comment                          |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0.. 63)  | mdToken     | *PVal* enthält ein vollständiges Token. Die-Funktion konvertiert die RID automatisch in ein vollständiges Token. |
| `iCodedToken`..`iCodedTokenMax`<br>(64.. 95) | mdToken | Bei der Rückgabe enthält *PVal* ein vollständiges Token. Die Funktion dekomprimiert das codedtoken automatisch in ein vollständiges Token. |
| `iSHORT` (96)            | Int16         | Automatisches Signieren auf 32-Bit.  |
| `iUSHORT` (97)           | UInt16        | Automatisches Signieren auf 32-Bit.  |
| `iLONG` (98)             | Int32         |                                        |
| `iULONG` (99)            | UInt32        |                                        |
| `iBYTE` (100)            | Byte          | Automatisches Signieren auf 32-Bit.  |
| `iSTRING` (101)          | String-Heap Index | *PVal* ist ein Index in den Zeichen folgen Heap. Verwenden Sie [IMetadataTables:: GetString](imetadatatables-getstring-method.md) , um den tatsächlichen Spalten Zeichen folgen Wert zu erhalten. |
| `iGUID` (102)            | GUID-Heap Index | *PVal* ist ein Index für den GUID-Heap. Verwenden Sie [IMetadataTables:: GetGuid](imetadatatables-getguid-method.md) , um den tatsächlichen Spalten-GUID-Wert zu erhalten. |
| `iBLOB` (103)            | BLOB-Heap Index | *PVal* ist ein Index im BLOB-Heap. Verwenden Sie [IMetadataTables:: GetBlob](imetadatatables-getblob-method.md) , um den tatsächlichen spaltenblob-Wert zu erhalten. |
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataTables-Schnittstelle](imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](imetadatatables2-interface.md)
