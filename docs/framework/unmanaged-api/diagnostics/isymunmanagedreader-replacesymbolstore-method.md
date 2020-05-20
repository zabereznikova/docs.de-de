---
title: ISymUnmanagedReader::ReplaceSymbolStore-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
ms.openlocfilehash: db2137146ded5200e05bbf88e23ae599f3eb7dec
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615448"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="9ada5-102">ISymUnmanagedReader::ReplaceSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="9ada5-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="9ada5-103">Ersetzt den vorhandenen Symbolspeicher durch einen Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="9ada5-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="9ada5-104">Diese Methode ähnelt der [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) -Methode, mit der Ausnahme, dass das angegebene Delta anstelle eines Updates als kompletter Ersatz fungiert.</span><span class="sxs-lookup"><span data-stu-id="9ada5-104">This method is similar to the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ada5-105">Sie müssen nur einen der `filename` Parameter oder angeben `pIStream` , nicht beides.</span><span class="sxs-lookup"><span data-stu-id="9ada5-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="9ada5-106">Wenn `filename` angegeben wird, wird der Symbol Speicher mit den Symbolen in dieser Datei aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9ada5-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="9ada5-107">Wenn `pIStream` angegeben wird, wird der Speicher mit den Daten aus der aktualisiert <xref:System.Runtime.InteropServices.ComTypes.IStream> .</span><span class="sxs-lookup"><span data-stu-id="9ada5-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ada5-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ada5-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ada5-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ada5-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="9ada5-110">in Der Name der Datei, die den Symbol Speicher enthält.</span><span class="sxs-lookup"><span data-stu-id="9ada5-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="9ada5-111">in Der Dateistream, der als Alternative zum- `filename` Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ada5-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ada5-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9ada5-112">Return Value</span></span>  
 <span data-ttu-id="9ada5-113">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9ada5-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ada5-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ada5-114">Requirements</span></span>  
 <span data-ttu-id="9ada5-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="9ada5-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ada5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ada5-116">See also</span></span>

- [<span data-ttu-id="9ada5-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ada5-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
