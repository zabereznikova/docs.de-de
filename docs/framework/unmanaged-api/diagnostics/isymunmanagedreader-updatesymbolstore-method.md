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
ms.openlocfilehash: e052d9b7b2abd57b176dfe3b00afac626d422c58
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446455"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>ISymUnmanagedReader::UpdateSymbolStore-Methode
Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher. Diese Methode wird in "Bearbeiten und Fortfahren"-Szenarios verwendet, um den Symbol Speicher zu aktualisieren, sodass er mit der ursprünglichen portablen ausführbaren Datei (PE-Datei) identisch ist.  
  
> [!NOTE]
> Sie müssen nur einen der Parameter `filename` oder `pIStream` angeben, nicht beides. Wenn `filename` angegeben wird, wird der Symbol Speicher mit den Symbolen in dieser Datei aktualisiert. Wenn `pIStream` angegeben wird, wird der Speicher mit den Daten des <xref:System.Runtime.InteropServices.ComTypes.IStream>aktualisiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Parameter  
 `filename`  
 in Der Name der Datei, die den Symbol Speicher enthält.  
  
 `pIStream`  
 in Der Dateistream, der als Alternative zum `filename`-Parameter verwendet wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
