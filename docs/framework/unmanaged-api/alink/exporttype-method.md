---
title: ExportType-Methode
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95ff27143453e7772b4a463fa66ca039bbb715fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226916"
---
# <a name="exporttype-method"></a><span data-ttu-id="942c5-102">ExportType-Methode</span><span class="sxs-lookup"><span data-stu-id="942c5-102">ExportType Method</span></span>
<span data-ttu-id="942c5-103">Gibt an, dass ein Typ exportiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="942c5-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="942c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="942c5-104">Syntax</span></span>  
  
```  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="942c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="942c5-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="942c5-106">Die ID der Assembly zum Exportieren aus.</span><span class="sxs-lookup"><span data-stu-id="942c5-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="942c5-107">Datei-Token "oder" Assembly-ID der Datei, die den exportierbaren Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="942c5-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="942c5-108">Token des Typs als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="942c5-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="942c5-109">Voll gekennzeichneten Typnamen als exportierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="942c5-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="942c5-110">`ComType` Flags, z. B. `tdPublic` oder `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="942c5-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="942c5-111">Dieser Parameter kann übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="942c5-111">This parameter may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="942c5-112">Empfängt die Token für den exportierten Typ.</span><span class="sxs-lookup"><span data-stu-id="942c5-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="942c5-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="942c5-113">Return Value</span></span>  
 <span data-ttu-id="942c5-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="942c5-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="942c5-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="942c5-115">Requirements</span></span>  
 <span data-ttu-id="942c5-116">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="942c5-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="942c5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="942c5-117">See also</span></span>

- [<span data-ttu-id="942c5-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="942c5-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="942c5-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="942c5-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="942c5-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="942c5-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
