---
title: ISymUnmanagedReader::ReplaceSymbolStore-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.ReplaceSymbolStore
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bedceac4661204bb72e59981450d7fee488857b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="ac423-102">ISymUnmanagedReader::ReplaceSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="ac423-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="ac423-103">Ersetzt den vorhandenen Symbolspeicher durch einen Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="ac423-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="ac423-104">Diese Methode ist vergleichbar mit der [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) -Methode, außer dass das angegebene Delta als eine vollständige Ersetzung statt ein Update fungiert.</span><span class="sxs-lookup"><span data-stu-id="ac423-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac423-105">Müssen Sie nur eine der angeben der `filename` oder `pIStream` Parameter, nicht beides.</span><span class="sxs-lookup"><span data-stu-id="ac423-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="ac423-106">Wenn `filename` angegeben ist, wird mit den Symbolen in dieser Datei der Symbolspeicher aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ac423-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="ac423-107">Wenn `pIStream` angegeben ist, wird der Speicher wird aktualisiert werden, mit den Daten aus der <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="ac423-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac423-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac423-108">Syntax</span></span>  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac423-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac423-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="ac423-110">[in] Der Name der Datei, die den Symbolspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="ac423-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="ac423-111">[in] Der Dateidatenstrom als Alternative zur verwendet die `filename` Parameter.</span><span class="sxs-lookup"><span data-stu-id="ac423-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac423-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ac423-112">Return Value</span></span>  
 <span data-ttu-id="ac423-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ac423-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac423-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac423-114">Requirements</span></span>  
 <span data-ttu-id="ac423-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ac423-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac423-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac423-116">See Also</span></span>  
 [<span data-ttu-id="ac423-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac423-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
