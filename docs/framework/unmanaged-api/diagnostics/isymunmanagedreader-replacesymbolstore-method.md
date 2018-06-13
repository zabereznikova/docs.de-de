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
ms.openlocfilehash: 03607cf96d73e96eef63fe62b86b50be02f34421
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428201"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="66b21-102">ISymUnmanagedReader::ReplaceSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="66b21-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="66b21-103">Ersetzt den vorhandenen Symbolspeicher durch einen Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="66b21-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="66b21-104">Diese Methode ist vergleichbar mit der [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) -Methode, außer dass das angegebene Delta als eine vollständige Ersetzung statt ein Update fungiert.</span><span class="sxs-lookup"><span data-stu-id="66b21-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66b21-105">Müssen Sie nur eine der angeben der `filename` oder `pIStream` Parameter, nicht beides.</span><span class="sxs-lookup"><span data-stu-id="66b21-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="66b21-106">Wenn `filename` angegeben ist, wird mit den Symbolen in dieser Datei der Symbolspeicher aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="66b21-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="66b21-107">Wenn `pIStream` angegeben ist, wird der Speicher wird aktualisiert werden, mit den Daten aus der <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="66b21-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66b21-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="66b21-108">Syntax</span></span>  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66b21-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="66b21-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="66b21-110">[in] Der Name der Datei, die den Symbolspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="66b21-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="66b21-111">[in] Der Dateidatenstrom als Alternative zur verwendet die `filename` Parameter.</span><span class="sxs-lookup"><span data-stu-id="66b21-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66b21-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="66b21-112">Return Value</span></span>  
 <span data-ttu-id="66b21-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="66b21-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66b21-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66b21-114">Requirements</span></span>  
 <span data-ttu-id="66b21-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="66b21-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66b21-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66b21-116">See Also</span></span>  
 [<span data-ttu-id="66b21-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66b21-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
