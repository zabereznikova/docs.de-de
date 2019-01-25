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
ms.openlocfilehash: 87dd256bfe8a067ad798bff77a172b936f2d6aab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649933"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="268ac-102">ISymUnmanagedWriter::GetDebugInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="268ac-102">ISymUnmanagedWriter::GetDebugInfo Method</span></span>
<span data-ttu-id="268ac-103">Gibt Informationen zurück, das für ein Compiler das Debugverzeichniseintrag im portierbare ausführbare Datei (PE)-Header zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="268ac-103">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="268ac-104">Alle Felder mit Ausnahme von füllt der Symbolwriter `TimeDateStamp` und `PointerToRawData`.</span><span class="sxs-lookup"><span data-stu-id="268ac-104">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="268ac-105">(Der Compiler ist zuständig für das diese zwei Felder entsprechend festlegen.)</span><span class="sxs-lookup"><span data-stu-id="268ac-105">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="268ac-106">Ein Compiler sollte diese Methode aufrufen, der Daten-Blob in der PE-Datei ausgeben, Festlegen von der `PointerToRawData` Feld IMAGE_DEBUG_DIRECTORY zeigen Sie auf die ausgegebenen Daten und das IMAGE_DEBUG_DIRECTORY in der PE-Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="268ac-106">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="268ac-107">Der Compiler sollte ebenfalls festgelegt. die `TimeDateStamp` -Feld auf die `TimeDateStamp` der PE-Datei generiert wird.</span><span class="sxs-lookup"><span data-stu-id="268ac-107">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="268ac-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="268ac-108">Syntax</span></span>  
  
```  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="268ac-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="268ac-109">Parameters</span></span>  
 `pIDD`  
 <span data-ttu-id="268ac-110">[in, out] Ein Zeiger auf ein IMAGE_DEBUG_DIRECTORY, die der Symbolwriter ausgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="268ac-110">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="268ac-111">[in] Ein `DWORD` , die die Größe der Debug-Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="268ac-111">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="268ac-112">[out] Ein Zeiger auf eine `DWORD` , empfängt die Größe des Puffers erforderlich, um die Debug-Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="268ac-112">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="268ac-113">[out] Ein Zeiger auf einen Puffer, der groß genug zum Speichern der Debugdaten für den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="268ac-113">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="268ac-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="268ac-114">Return Value</span></span>  
 <span data-ttu-id="268ac-115">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="268ac-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="268ac-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="268ac-116">Requirements</span></span>  
 <span data-ttu-id="268ac-117">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="268ac-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="268ac-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="268ac-118">See also</span></span>
- [<span data-ttu-id="268ac-119">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="268ac-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
