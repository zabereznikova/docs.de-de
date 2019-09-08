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
ms.openlocfilehash: 5db205993bc1a0665dc0003948ce805813251f48
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787450"
---
# <a name="getfiledef-method"></a><span data-ttu-id="60768-102">GetFileDef-Methode</span><span class="sxs-lookup"><span data-stu-id="60768-102">GetFileDef Method</span></span>
<span data-ttu-id="60768-103">Ruft das tatsächliche FileDef-Token ab, das in den Metadaten verwendet wird (im Gegensatz zum von ALink zugewiesenen Token).</span><span class="sxs-lookup"><span data-stu-id="60768-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60768-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60768-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="60768-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="60768-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="60768-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="60768-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="60768-107">Token der hinzugefügten Datei, das von der AddFile-Methode oder der AddImport-Methode abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="60768-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="60768-108">Empfängt das FileDef-Token.</span><span class="sxs-lookup"><span data-stu-id="60768-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60768-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="60768-109">Return Value</span></span>  
 <span data-ttu-id="60768-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="60768-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60768-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60768-111">Requirements</span></span>  
 <span data-ttu-id="60768-112">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="60768-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60768-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60768-113">See also</span></span>

- [<span data-ttu-id="60768-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60768-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="60768-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60768-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="60768-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="60768-116">ALink API</span></span>](index.md)
