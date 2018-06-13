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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81f9db872e9904d2297221e266be710837d0fb66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427381"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="246d9-102">ISymUnmanagedReader::UpdateSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="246d9-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="246d9-103">Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="246d9-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="246d9-104">Diese Methode wird in bearbeiten und Fortfahren-Szenarien verwendet, um den Symbolspeicher Deltas mit der ursprünglichen portierbare ausführbare Datei (PE) Datei entsprechend zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="246d9-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="246d9-105">Müssen Sie nur eine der angeben der `filename` oder `pIStream` Parameter, nicht beides.</span><span class="sxs-lookup"><span data-stu-id="246d9-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="246d9-106">Wenn `filename` angegeben ist, wird mit den Symbolen in dieser Datei der Symbolspeicher aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="246d9-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="246d9-107">Wenn `pIStream` angegeben ist, wird der Speicher wird aktualisiert werden, mit den Daten aus der <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="246d9-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="246d9-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="246d9-108">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="246d9-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="246d9-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="246d9-110">[in] Der Name der Datei, die den Symbolspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="246d9-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="246d9-111">[in] Der Dateidatenstrom als Alternative zur verwendet die `filename` Parameter.</span><span class="sxs-lookup"><span data-stu-id="246d9-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="246d9-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="246d9-112">Return Value</span></span>  
 <span data-ttu-id="246d9-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="246d9-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="246d9-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="246d9-114">Requirements</span></span>  
 <span data-ttu-id="246d9-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="246d9-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246d9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="246d9-116">See Also</span></span>  
 [<span data-ttu-id="246d9-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="246d9-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
