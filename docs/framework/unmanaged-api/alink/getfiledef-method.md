---
title: GetFileDef-Methode
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9153c9b3735e265d59ba072f747c92434c95d9ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789869"
---
# <a name="getfiledef-method"></a><span data-ttu-id="fdc77-102">GetFileDef-Methode</span><span class="sxs-lookup"><span data-stu-id="fdc77-102">GetFileDef Method</span></span>
<span data-ttu-id="fdc77-103">Ruft ab, das tatsächliche FileDef-Token, die in den Metadaten (im Gegensatz zu das Token von ALink zugewiesen wird) verwendet.</span><span class="sxs-lookup"><span data-stu-id="fdc77-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc77-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdc77-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdc77-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fdc77-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fdc77-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="fdc77-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="fdc77-107">Der hinzugefügten Datei AddFile-Methode oder AddImport-Methode abgerufene Token.</span><span class="sxs-lookup"><span data-stu-id="fdc77-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="fdc77-108">Empfängt die FileDef-Token.</span><span class="sxs-lookup"><span data-stu-id="fdc77-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdc77-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fdc77-109">Return Value</span></span>  
 <span data-ttu-id="fdc77-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="fdc77-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdc77-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fdc77-111">Requirements</span></span>  
 <span data-ttu-id="fdc77-112">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="fdc77-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc77-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdc77-113">See also</span></span>

- [<span data-ttu-id="fdc77-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fdc77-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="fdc77-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fdc77-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="fdc77-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="fdc77-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
