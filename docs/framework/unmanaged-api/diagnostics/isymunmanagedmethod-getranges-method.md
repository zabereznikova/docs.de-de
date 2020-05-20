---
title: ISymUnmanagedMethod::GetRanges-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
ms.openlocfilehash: cd5d1f2d59d3e55ba454f23d2e5dd4b1316c0df4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615175"
---
# <a name="isymunmanagedmethodgetranges-method"></a>ISymUnmanagedMethod::GetRanges-Methode
Gibt ein Array von Start-und Endoffset Paaren zurück, die den Bereichen der Microsoft Intermediate Language (MSIL) entsprechen, die von der Position innerhalb dieser Methode abgedeckt werden, wenn eine Position in einem Dokument verfügbar ist. Das Array ist ein Array aus ganzen Zahlen und hat das Format [Start, End, Start, End]. Die Anzahl der Bereichs Paare ist die Länge des Arrays dividiert durch 2.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `document`  
 in Das Dokument, für das der Offset angefordert wird.  
  
 `line`  
 in Die Dokument Zeile, die den Bereichen entspricht.  
  
 `column`  
 in Die Dokument Spalte, die den Bereichen entspricht.  
  
 `cRanges`  
 [in] Die Größe des `ranges`-Arrays.  
  
 `pcRanges`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der Bereiche erforderlich ist.  
  
 `ranges`  
 vorgenommen Ein Zeiger auf den Puffer, der die Bereiche empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedMethod-Schnittstelle](isymunmanagedmethod-interface.md)
