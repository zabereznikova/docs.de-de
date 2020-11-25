---
title: AddImport-Methode
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
ms.openlocfilehash: cf73ada36be66edb3fa267d61873ae9acb088a34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717044"
---
# <a name="addimport-method"></a><span data-ttu-id="dbb14-102">AddImport-Methode</span><span class="sxs-lookup"><span data-stu-id="dbb14-102">AddImport Method</span></span>

<span data-ttu-id="dbb14-103">Fügt der Assembly Importe hinzu.</span><span class="sxs-lookup"><span data-stu-id="dbb14-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbb14-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbb14-104">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbb14-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dbb14-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="dbb14-106">Eindeutige ID der Assembly, die erweitert werden soll.</span><span class="sxs-lookup"><span data-stu-id="dbb14-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="dbb14-107">Die eindeutige ID, die von der [ImportFile-Methode](importfile-method.md)abgerufen wird, der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="dbb14-107">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="dbb14-108">Com+-FileDef-Flags, z `ffContainsNoMetaData` `ffWriteable` . b. und.</span><span class="sxs-lookup"><span data-stu-id="dbb14-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="dbb14-109">`dwFlags` wird an die [DefineFile-Methode](../metadata/imetadataassemblyemit-definefile-method.md)übermittelt.</span><span class="sxs-lookup"><span data-stu-id="dbb14-109">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="dbb14-110">Zeiger auf das Token, das die ID für die resultierende Datei empfängt.</span><span class="sxs-lookup"><span data-stu-id="dbb14-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbb14-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dbb14-111">Return Value</span></span>  

 <span data-ttu-id="dbb14-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="dbb14-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbb14-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dbb14-113">Requirements</span></span>  

 <span data-ttu-id="dbb14-114">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="dbb14-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb14-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dbb14-115">See also</span></span>

- [<span data-ttu-id="dbb14-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbb14-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="dbb14-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbb14-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="dbb14-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="dbb14-118">ALink API</span></span>](index.md)
