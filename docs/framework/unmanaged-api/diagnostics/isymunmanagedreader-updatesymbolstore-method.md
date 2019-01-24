---
title: ISymUnmanagedReader::UpdateSymbolStore-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e5ae097314a935bc06272c0e8febfbaad620f13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667634"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>ISymUnmanagedReader::UpdateSymbolStore-Methode
Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher. Diese Methode wird in Szenarien mit bearbeiten und Fortfahren verwendet, um den Symbolspeicher Änderungen an der ursprünglichen übertragbaren ausführbaren Datei (PE) Datei entsprechend zu aktualisieren.  
  
> [!NOTE]
>  Sie müssen nur eine der angeben der `filename` oder `pIStream` nicht beide Parameter. Wenn `filename` angegeben ist, wird für die Symbole in der Datei der Symbolspeicher aktualisiert werden. Wenn `pIStream` angegeben ist, wird mit den Daten aus der Speicher aktualisiert werden die <xref:System.Runtime.InteropServices.ComTypes.IStream>.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 [in] Der Name der Datei, die den Symbolspeicher enthält.  
  
 `pIStream`  
 [in] Als Alternative zu den Datei-Stream der `filename` Parameter.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
