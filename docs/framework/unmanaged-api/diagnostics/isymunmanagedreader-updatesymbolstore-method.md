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
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="aef06-102">ISymUnmanagedReader::UpdateSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="aef06-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="aef06-103">Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="aef06-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="aef06-104">Diese Methode wird in "Bearbeiten und Fortfahren"-Szenarios verwendet, um den Symbol Speicher zu aktualisieren, sodass er mit der ursprünglichen portablen ausführbaren Datei (PE-Datei) identisch ist.</span><span class="sxs-lookup"><span data-stu-id="aef06-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aef06-105">Sie müssen nur einen der Parameter `filename` oder `pIStream` angeben, nicht beides.</span><span class="sxs-lookup"><span data-stu-id="aef06-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="aef06-106">Wenn `filename` angegeben wird, wird der Symbol Speicher mit den Symbolen in dieser Datei aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="aef06-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="aef06-107">Wenn `pIStream` angegeben wird, wird der Speicher mit den Daten des <xref:System.Runtime.InteropServices.ComTypes.IStream>aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="aef06-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aef06-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="aef06-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aef06-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="aef06-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="aef06-110">in Der Name der Datei, die den Symbol Speicher enthält.</span><span class="sxs-lookup"><span data-stu-id="aef06-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="aef06-111">in Der Dateistream, der als Alternative zum `filename`-Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aef06-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aef06-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aef06-112">Return Value</span></span>  
 <span data-ttu-id="aef06-113">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="aef06-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aef06-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="aef06-114">Requirements</span></span>  
 <span data-ttu-id="aef06-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="aef06-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef06-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aef06-116">See also</span></span>

- [<span data-ttu-id="aef06-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aef06-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
