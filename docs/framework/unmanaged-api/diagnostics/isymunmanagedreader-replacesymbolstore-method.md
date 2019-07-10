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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 525ec4828fb942aeb447940ea68a523cd7c69140
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736729"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="e9dd6-102">ISymUnmanagedReader::ReplaceSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="e9dd6-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="e9dd6-103">Ersetzt den vorhandenen Symbolspeicher durch einen Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="e9dd6-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="e9dd6-104">Diese Methode ähnelt der [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) -Methode, mit der Ausnahme an, dass das angegebene Delta vollständig ersetzt, sondern als ein Update fungiert.</span><span class="sxs-lookup"><span data-stu-id="e9dd6-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9dd6-105">Sie müssen nur eine der angeben der `filename` oder `pIStream` nicht beide Parameter.</span><span class="sxs-lookup"><span data-stu-id="e9dd6-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="e9dd6-106">Wenn `filename` angegeben ist, wird für die Symbole in der Datei der Symbolspeicher aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e9dd6-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="e9dd6-107">Wenn `pIStream` angegeben ist, wird mit den Daten aus der Speicher aktualisiert werden die <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="e9dd6-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9dd6-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9dd6-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9dd6-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9dd6-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="e9dd6-110">[in] Der Name der Datei mit dem Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="e9dd6-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="e9dd6-111">[in] Als Alternative zu den Datei-Stream der `filename` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e9dd6-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9dd6-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e9dd6-112">Return Value</span></span>  
 <span data-ttu-id="e9dd6-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e9dd6-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9dd6-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9dd6-114">Requirements</span></span>  
 <span data-ttu-id="e9dd6-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e9dd6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9dd6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9dd6-116">See also</span></span>

- [<span data-ttu-id="e9dd6-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9dd6-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
