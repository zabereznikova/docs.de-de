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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bbe8a43f44d59249abc713c95fce31f1fb9a5993
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148667"
---
# <a name="addimport-method"></a><span data-ttu-id="786a7-102">AddImport-Methode</span><span class="sxs-lookup"><span data-stu-id="786a7-102">AddImport Method</span></span>
<span data-ttu-id="786a7-103">Importe und die Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="786a7-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="786a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="786a7-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="786a7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="786a7-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="786a7-106">Eindeutige ID der Assembly, die erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="786a7-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="786a7-107">Eindeutige ID, die aus abgerufen [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="786a7-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="786a7-108">COM+ FileDef-flags, z. B. `ffContainsNoMetaData` und `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="786a7-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> `dwFlags` <span data-ttu-id="786a7-109">wird zum übergeben [DefineFile-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="786a7-109">is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="786a7-110">Zeiger auf das Token, das die ID für die resultierende Datei erhält.</span><span class="sxs-lookup"><span data-stu-id="786a7-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="786a7-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="786a7-111">Return Value</span></span>  
 <span data-ttu-id="786a7-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="786a7-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="786a7-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="786a7-113">Requirements</span></span>  
 <span data-ttu-id="786a7-114">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="786a7-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786a7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="786a7-115">See also</span></span>

- [<span data-ttu-id="786a7-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="786a7-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="786a7-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="786a7-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="786a7-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="786a7-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
