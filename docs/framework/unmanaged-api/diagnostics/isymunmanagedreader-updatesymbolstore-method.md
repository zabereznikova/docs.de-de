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
ms.openlocfilehash: 6670d985eed4c55550b23d3f4110ee20f3b75661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675827"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="a5109-102">ISymUnmanagedReader::UpdateSymbolStore-Methode</span><span class="sxs-lookup"><span data-stu-id="a5109-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>

<span data-ttu-id="a5109-103">Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="a5109-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="a5109-104">Diese Methode wird in "Bearbeiten und Fortfahren"-Szenarios verwendet, um den Symbol Speicher zu aktualisieren, sodass er mit der ursprünglichen portablen ausführbaren Datei (PE-Datei) identisch ist.</span><span class="sxs-lookup"><span data-stu-id="a5109-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5109-105">Sie müssen nur einen der `filename` Parameter oder angeben `pIStream` , nicht beides.</span><span class="sxs-lookup"><span data-stu-id="a5109-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="a5109-106">Wenn `filename` angegeben wird, wird der Symbol Speicher mit den Symbolen in dieser Datei aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="a5109-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="a5109-107">Wenn `pIStream` angegeben wird, wird der Speicher mit den Daten aus der aktualisiert <xref:System.Runtime.InteropServices.ComTypes.IStream> .</span><span class="sxs-lookup"><span data-stu-id="a5109-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5109-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5109-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5109-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="a5109-109">Parameters</span></span>  

 `filename`  
 <span data-ttu-id="a5109-110">in Der Name der Datei, die den Symbol Speicher enthält.</span><span class="sxs-lookup"><span data-stu-id="a5109-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="a5109-111">in Der Dateistream, der als Alternative zum- `filename` Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5109-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5109-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a5109-112">Return Value</span></span>  

 <span data-ttu-id="a5109-113">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a5109-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5109-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a5109-114">Requirements</span></span>  

 <span data-ttu-id="a5109-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="a5109-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5109-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5109-116">See also</span></span>

- [<span data-ttu-id="a5109-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5109-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
