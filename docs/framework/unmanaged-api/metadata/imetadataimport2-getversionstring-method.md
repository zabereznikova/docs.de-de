---
title: IMetaDataImport2::GetVersionString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a01b4203145f6ffee4e3a11a3526f0b83e3dc741
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154621"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="a7732-102">IMetaDataImport2::GetVersionString-Methode</span><span class="sxs-lookup"><span data-stu-id="a7732-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="a7732-103">Ruft die Version der Laufzeit, die verwendet wurde, zur Erstellung der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="a7732-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7732-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7732-104">Syntax</span></span>  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7732-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7732-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="a7732-106">[out] Ein Array zum Speichern der Zeichenfolge, die die Version angibt.</span><span class="sxs-lookup"><span data-stu-id="a7732-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="a7732-107">[in] Die Größe in Breitzeichen, der die `pwzBuf` Array.</span><span class="sxs-lookup"><span data-stu-id="a7732-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="a7732-108">[out] Die Anzahl von Breitzeichen, einschließlich eines null-Terminators zurückgegeben wird, der `pwzBuf` Array.</span><span class="sxs-lookup"><span data-stu-id="a7732-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7732-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7732-109">Remarks</span></span>  
 <span data-ttu-id="a7732-110">Die `GetVersionString` Methode ruft die für die Version der im aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="a7732-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="a7732-111">Wenn der Bereich nicht gespeichert wurde, hat keine für die Version, und eine leere Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a7732-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7732-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7732-112">Requirements</span></span>  
 <span data-ttu-id="a7732-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7732-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7732-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7732-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7732-115">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a7732-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="a7732-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a7732-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7732-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7732-117">See also</span></span>

- [<span data-ttu-id="a7732-118">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7732-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="a7732-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7732-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
