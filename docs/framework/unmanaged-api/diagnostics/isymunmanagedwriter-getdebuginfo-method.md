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
ms.openlocfilehash: dcab63b603d4a9a8e1430228043d2a5e597bbf4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678291"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="532b2-102">ISymUnmanagedWriter::GetDebugInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="532b2-102">ISymUnmanagedWriter::GetDebugInfo Method</span></span>

<span data-ttu-id="532b2-103">Gibt die erforderlichen Informationen zurück, damit ein Compiler den Debugverzeichniseintrag im PE-Dateiheader schreiben muss.</span><span class="sxs-lookup"><span data-stu-id="532b2-103">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="532b2-104">Der Symbolwriter füllt alle Felder mit Ausnahme von `TimeDateStamp` und aus `PointerToRawData` .</span><span class="sxs-lookup"><span data-stu-id="532b2-104">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="532b2-105">(Der Compiler ist dafür verantwortlich, diese beiden Felder entsprechend festzulegen.)</span><span class="sxs-lookup"><span data-stu-id="532b2-105">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="532b2-106">Ein Compiler sollte diese Methode abrufen, das Daten-BLOB an die PE-Datei ausgeben, das Feld in der IMAGE_DEBUG_DIRECTORY so festlegen, dass es `PointerToRawData` auf die ausgegebenen Daten verweist, und die IMAGE_DEBUG_DIRECTORY in die PE-Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="532b2-106">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="532b2-107">Der Compiler sollte außerdem festlegen `TimeDateStamp` , dass das-Feld gleich dem `TimeDateStamp` der generierten PE-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="532b2-107">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="532b2-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="532b2-108">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="532b2-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="532b2-109">Parameters</span></span>  

 `pIDD`  
 <span data-ttu-id="532b2-110">[in, out] Ein Zeiger auf einen IMAGE_DEBUG_DIRECTORY, den der Symbolwriter ausfüllen wird.</span><span class="sxs-lookup"><span data-stu-id="532b2-110">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="532b2-111">in Ein-Wert `DWORD` , der die Größe der Debugdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="532b2-111">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="532b2-112">vorgenommen Ein Zeiger auf einen `DWORD` , der die Größe des Puffers empfängt, der zum enthalten der Debugdaten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="532b2-112">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="532b2-113">vorgenommen Ein Zeiger auf einen Puffer, der groß genug ist, um die Debugdaten für den Symbol Speicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="532b2-113">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="532b2-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="532b2-114">Return Value</span></span>  

 <span data-ttu-id="532b2-115">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="532b2-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="532b2-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="532b2-116">Requirements</span></span>  

 <span data-ttu-id="532b2-117">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="532b2-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="532b2-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="532b2-118">See also</span></span>

- [<span data-ttu-id="532b2-119">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="532b2-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
