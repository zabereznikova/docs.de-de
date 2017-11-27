---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 77c573865ad9fba14259e9bb1538a15cb3067925
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a>ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo-Methode
Ruft die Symbolinformationen für die Suche ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cSearchInfo`  
 [in] Ein `ULONG32` , der angibt, dass der Größe des `rgpSearchInfo`.  
  
 `pcSearchInfo`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des Puffers benötigt, um die Suchinformationen aufzunehmen.  
  
 `rgpSearchInfo`  
 [out] Ein Zeiger, der festgelegt wird, wird auf das zurückgegebene [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
