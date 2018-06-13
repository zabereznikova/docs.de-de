---
title: AddImport Methode1
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
ms.openlocfilehash: 98fefc0240f6496a3e7bfb491e27a57e98cfea1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404065"
---
# <a name="addimport-method1"></a><span data-ttu-id="55f60-102">AddImport Methode1</span><span class="sxs-lookup"><span data-stu-id="55f60-102">AddImport Method1</span></span>
<span data-ttu-id="55f60-103">Importe und die Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="55f60-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55f60-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55f60-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55f60-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="55f60-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="55f60-106">Eindeutige ID der Assembly, die erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="55f60-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="55f60-107">Eindeutige ID, die aus abgerufen [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="55f60-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="55f60-108">COM+-FileDef-flags, z. B. `ffContainsNoMetaData` und `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="55f60-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="55f60-109">`dwFlags` wird zum übergeben [DefineFile-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="55f60-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="55f60-110">Zeiger auf Token, das die ID für die resultierende Datei empfängt.</span><span class="sxs-lookup"><span data-stu-id="55f60-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55f60-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="55f60-111">Return Value</span></span>  
 <span data-ttu-id="55f60-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="55f60-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55f60-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55f60-113">Requirements</span></span>  
 <span data-ttu-id="55f60-114">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="55f60-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55f60-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55f60-115">See Also</span></span>  
 [<span data-ttu-id="55f60-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55f60-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="55f60-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55f60-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="55f60-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="55f60-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
