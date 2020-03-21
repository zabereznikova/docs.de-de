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
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177139"
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
 [in] Der Index der Tabelle.  
  
 `ixCol`  
 [in] Der Index der Spalte in der Tabelle.  
  
 `rid`  
 [in] Der Index der Zeile in der Tabelle.  
  
 `pVal`  
 [out] Ein Zeiger auf den Wert in der Zelle.  

## <a name="remarks"></a>Bemerkungen

Die Interpretation des zurückgegebenen `pVal` Werts hängt vom Spaltentyp ab. Der Spaltentyp kann durch Aufrufen von [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md)bestimmt werden.

- Die **GetColumn-Methode** konvertiert automatisch Spalten vom Typ **Rid** oder `mdToken` **CodedToken** in vollständige 32-Bit-Werte.
- Außerdem werden 8-Bit- oder 16-Bit-Werte automatisch in vollständige 32-Bit-Werte konvertiert.
- Bei *Heaptypspalten* ist das zurückgegebene *pVal* ein Index in den entsprechenden Heap.

| Spaltentyp              | pVal enthält | Comment                          |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0..63)  | mdToken     | *pVal* enthält ein vollständiges Token. Die Funktion konvertiert den Rid automatisch in ein vollständiges Token. |
| `iCodedToken`..`iCodedTokenMax`<br>(64..95) | mdToken | Nach der Rückkehr enthält *pVal* einen vollständigen Token. Die Funktion dekomprimiert den CodedToken automatisch in ein vollständiges Token. |
| `iSHORT`(96)            | Int16         | Automatisch sign-extended auf 32-Bit.  |
| `iUSHORT`(97)           | UInt16        | Automatisch sign-extended auf 32-Bit.  |
| `iLONG`(98)             | Int32         |                                        |
| `iULONG`(99)            | UInt32        |                                        |
| `iBYTE`(100)            | Byte          | Automatisch sign-extended auf 32-Bit.  |
| `iSTRING`(101)          | String-Heap-Index | *pVal* ist ein Index im String-Heap. Verwenden Sie [IMetadataTables::GetString,](imetadatatables-getstring-method.md) um den tatsächlichen Spaltenzeichenfolgenwert abzurufen. |
| `iGUID`(102)            | Guid-Heapindex | *pVal* ist ein Index im Guid-Heap. Verwenden Sie [IMetadataTables::GetGuid,](imetadatatables-getguid-method.md) um den tatsächlichen Spalten-Guid-Wert abzurufen. |
| `iBLOB`(103)            | Blob-Heap-Index | *pVal* ist ein Index im Blob-Heap. Verwenden Sie [IMetadataTables::GetBlob,](imetadatatables-getblob-method.md) um den tatsächlichen Spalten-Blobwert abzurufen. |
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataTables-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
