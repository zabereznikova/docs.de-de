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
ms.openlocfilehash: 2b901a3dac499f1ce3f843c59122dd8fd5022147
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427960"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>ISymUnmanagedWriter::GetDebugInfo-Methode
Gibt die erforderlichen Informationen zurück, damit ein Compiler den Debugverzeichniseintrag im PE-Dateiheader schreiben muss. Der Symbolwriter füllt alle Felder mit Ausnahme von `TimeDateStamp` und `PointerToRawData`aus. (Der Compiler ist dafür verantwortlich, diese beiden Felder entsprechend festzulegen.)  
  
 Ein Compiler sollte diese Methode abrufen, das Daten-BLOB an die PE-Datei ausgeben, das `PointerToRawData`-Feld im IMAGE_DEBUG_DIRECTORY so festlegen, dass es auf die ausgegebenen Daten verweist, und die IMAGE_DEBUG_DIRECTORY in die PE-Datei schreiben. Der Compiler sollte auch das `TimeDateStamp`-Feld so festlegen, dass es dem `TimeDateStamp` der generierten PE-Datei entspricht.  
  
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
 [in, out] Ein Zeiger auf einen IMAGE_DEBUG_DIRECTORY, den der Symbolwriter ausfüllen wird.  
  
 `cData`  
 in Eine `DWORD`, die die Größe der Debugdaten enthält.  
  
 `pcData`  
 vorgenommen Ein Zeiger auf einen `DWORD`, der die Größe des Puffers empfängt, der zum enthalten der Debugdaten erforderlich ist.  
  
 `data`  
 vorgenommen Ein Zeiger auf einen Puffer, der groß genug ist, um die Debugdaten für den Symbol Speicher zu speichern.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
