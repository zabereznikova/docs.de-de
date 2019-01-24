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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6afe0f0d8780a93a7d98f24a11bb67ef65ebf63
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604274"
---
# <a name="isymunmanagedmethodgetranges-method"></a>ISymUnmanagedMethod::GetRanges-Methode
Gibt bei Angabe einer Position in einem Dokument ein Array von Start- / Endoffsetpaaren, die entsprechen, die den Bereichen Microsoft intermediate Language (MSIL), die die Position innerhalb dieser Methode abgedeckt werden. Das Array ist ein Array von ganzen Zahlen und weist das Format ["Start", "End", "Start", "Ende"]. Die Anzahl der Bereichspaare ist die Länge des Arrays geteilt durch 2.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `document`  
 [in] Das Dokument, für das der Offset angefordert wird.  
  
 `line`  
 [in] Die Dokumentzeile, die den Bereichen entspricht.  
  
 `column`  
 [in] Die Dokumentspalte, die den Bereichen entspricht.  
  
 `cRanges`  
 [in] Die Größe des `ranges`-Arrays.  
  
 `pcRanges`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers erforderlich, um die Bereiche enthalten.  
  
 `ranges`  
 [out] Ein Zeiger auf den Puffer, der die Bereiche empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
