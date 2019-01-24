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
ms.openlocfilehash: 3e5ae097314a935bc06272c0e8febfbaad620f13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667634"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="e5549-102">ISymUnmanagedReader::UpdateSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="e5549-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="e5549-103">Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="e5549-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="e5549-104">Diese Methode wird in Szenarien mit bearbeiten und Fortfahren verwendet, um den Symbolspeicher Änderungen an der ursprünglichen übertragbaren ausführbaren Datei (PE) Datei entsprechend zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e5549-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5549-105">Sie müssen nur eine der angeben der `filename` oder `pIStream` nicht beide Parameter.</span><span class="sxs-lookup"><span data-stu-id="e5549-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="e5549-106">Wenn `filename` angegeben ist, wird für die Symbole in der Datei der Symbolspeicher aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e5549-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="e5549-107">Wenn `pIStream` angegeben ist, wird mit den Daten aus der Speicher aktualisiert werden die <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="e5549-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5549-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5549-108">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5549-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5549-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="e5549-110">[in] Der Name der Datei, die den Symbolspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="e5549-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="e5549-111">[in] Als Alternative zu den Datei-Stream der `filename` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e5549-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5549-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e5549-112">Return Value</span></span>  
 <span data-ttu-id="e5549-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e5549-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5549-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5549-114">Requirements</span></span>  
 <span data-ttu-id="e5549-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e5549-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5549-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5549-116">See also</span></span>
- [<span data-ttu-id="e5549-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5549-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
