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
ms.openlocfilehash: 84cf5ac9eab5749d3bdc63670fe5c31bfb62abcd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490406"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="17709-102">IMetaDataImport2::GetVersionString-Methode</span><span class="sxs-lookup"><span data-stu-id="17709-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="17709-103">Ruft die Versionsnummer der Laufzeit ab, die zum Erstellen der Assembly verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="17709-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17709-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17709-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17709-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="17709-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="17709-106">vorgenommen Ein Array zum Speichern der Zeichenfolge, die die Version angibt.</span><span class="sxs-lookup"><span data-stu-id="17709-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="17709-107">in Die Größe des Arrays (in breit Zeichen) `pwzBuf` .</span><span class="sxs-lookup"><span data-stu-id="17709-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="17709-108">vorgenommen Die Anzahl der breit Zeichen (einschließlich eines NULL-Terminator), die im Array zurückgegeben werden `pwzBuf` .</span><span class="sxs-lookup"><span data-stu-id="17709-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17709-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="17709-109">Remarks</span></span>  
 <span data-ttu-id="17709-110">Die `GetVersionString` -Methode ruft die integrierte Version des aktuellen Metadatenbereichs ab.</span><span class="sxs-lookup"><span data-stu-id="17709-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="17709-111">Wenn der Bereich noch nicht gespeichert wurde, verfügt er nicht über eine integrierte Version, und es wird eine leere Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="17709-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17709-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="17709-112">Requirements</span></span>  
 <span data-ttu-id="17709-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17709-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17709-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="17709-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="17709-115">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="17709-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="17709-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17709-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17709-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="17709-117">See also</span></span>

- [<span data-ttu-id="17709-118">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17709-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="17709-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17709-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
