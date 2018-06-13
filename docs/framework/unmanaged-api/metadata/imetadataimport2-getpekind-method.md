---
title: IMetaDataImport2::GetPEKind-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c938ef8783a122dec2a5f5bd3775661d68fba62c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449402"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="c6be6-102">IMetaDataImport2::GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="c6be6-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="c6be6-103">Ruft einen Wert, der die Art des Codes in der portierbaren ausführbaren Datei (PE) kennzeichnen Datei, in der Regel eine DLL oder EXE-Datei, die im aktuellen Metadatenbereich definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c6be6-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6be6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6be6-104">Syntax</span></span>  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6be6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6be6-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="c6be6-106">[out] Ein Zeiger auf den Wert der [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) Enumeration, die die PE-Datei beschreibt.</span><span class="sxs-lookup"><span data-stu-id="c6be6-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="c6be6-107">[out] Ein Zeiger auf einen Wert ab, die Architektur des Computers identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c6be6-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="c6be6-108">Finden Sie im nächsten Abschnitt Mögliche Werte.</span><span class="sxs-lookup"><span data-stu-id="c6be6-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6be6-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6be6-109">Remarks</span></span>  
 <span data-ttu-id="c6be6-110">Der referenzierte Wert der `pdwMachine` Parameter kann einen der folgenden sein.</span><span class="sxs-lookup"><span data-stu-id="c6be6-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="c6be6-111">Wert</span><span class="sxs-lookup"><span data-stu-id="c6be6-111">Value</span></span>|<span data-ttu-id="c6be6-112">Architektur des Computers</span><span class="sxs-lookup"><span data-stu-id="c6be6-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="c6be6-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="c6be6-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="c6be6-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="c6be6-114">0x014C</span></span>|<span data-ttu-id="c6be6-115">x86</span><span class="sxs-lookup"><span data-stu-id="c6be6-115">x86</span></span>|  
|<span data-ttu-id="c6be6-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="c6be6-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="c6be6-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="c6be6-117">0x0200</span></span>|<span data-ttu-id="c6be6-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="c6be6-118">Intel IPF</span></span>|  
|<span data-ttu-id="c6be6-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="c6be6-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="c6be6-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="c6be6-120">0x8664</span></span>|<span data-ttu-id="c6be6-121">x64</span><span class="sxs-lookup"><span data-stu-id="c6be6-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6be6-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6be6-122">Requirements</span></span>  
 <span data-ttu-id="c6be6-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6be6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6be6-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c6be6-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6be6-125">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c6be6-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6be6-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6be6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6be6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6be6-127">See Also</span></span>  
 [<span data-ttu-id="c6be6-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6be6-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="c6be6-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6be6-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="c6be6-130">CorPEKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c6be6-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
