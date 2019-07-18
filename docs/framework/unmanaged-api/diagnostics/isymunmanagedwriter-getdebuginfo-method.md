---
title: ISymUnmanagedWriter::GetDebugInfo-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8737885015055994bff3f6066bccb551f19f74f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777309"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>ISymUnmanagedWriter::GetDebugInfo-Methode
Gibt Informationen zurück, das für ein Compiler das Debugverzeichniseintrag im portierbare ausführbare Datei (PE)-Header zu schreiben. Alle Felder mit Ausnahme von füllt der Symbolwriter `TimeDateStamp` und `PointerToRawData`. (Der Compiler ist zuständig für das diese zwei Felder entsprechend festlegen.)  
  
 Ein Compiler sollte diese Methode aufrufen, der Daten-Blob in der PE-Datei ausgeben, Festlegen von der `PointerToRawData` Feld IMAGE_DEBUG_DIRECTORY zeigen Sie auf die ausgegebenen Daten und das IMAGE_DEBUG_DIRECTORY in der PE-Datei schreiben. Der Compiler sollte ebenfalls festgelegt. die `TimeDateStamp` -Feld auf die `TimeDateStamp` der PE-Datei generiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `pIDD`  
 [in, out] Ein Zeiger auf ein IMAGE_DEBUG_DIRECTORY, die der Symbolwriter ausgefüllt wird.  
  
 `cData`  
 [in] Ein `DWORD` , die die Größe der Debug-Daten enthält.  
  
 `pcData`  
 [out] Ein Zeiger auf eine `DWORD` , empfängt die Größe des Puffers erforderlich, um die Debug-Daten enthalten.  
  
 `data`  
 [out] Ein Zeiger auf einen Puffer, der groß genug zum Speichern der Debugdaten für den Symbolspeicher.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
