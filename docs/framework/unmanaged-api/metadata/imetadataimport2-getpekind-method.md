---
title: IMetaDataImport2::GetPEKind-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetPEKind
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8dc31877ba3550fa8faf610b831dfd2e7b313ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="0bbd2-102">IMetaDataImport2::GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="0bbd2-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="0bbd2-103">Ruft einen Wert, der die Art des Codes in der portierbaren ausführbaren Datei (PE) kennzeichnen Datei, in der Regel eine DLL oder EXE-Datei, die im aktuellen Metadatenbereich definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0bbd2-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bbd2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bbd2-104">Syntax</span></span>  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0bbd2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0bbd2-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="0bbd2-106">[out] Ein Zeiger auf den Wert der [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) Enumeration, die die PE-Datei beschreibt.</span><span class="sxs-lookup"><span data-stu-id="0bbd2-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="0bbd2-107">[out] Ein Zeiger auf einen Wert ab, die Architektur des Computers identifiziert.</span><span class="sxs-lookup"><span data-stu-id="0bbd2-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="0bbd2-108">Finden Sie im nächsten Abschnitt Mögliche Werte.</span><span class="sxs-lookup"><span data-stu-id="0bbd2-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bbd2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0bbd2-109">Remarks</span></span>  
 <span data-ttu-id="0bbd2-110">Der referenzierte Wert der `pdwMachine` Parameter kann einen der folgenden sein.</span><span class="sxs-lookup"><span data-stu-id="0bbd2-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="0bbd2-111">Wert</span><span class="sxs-lookup"><span data-stu-id="0bbd2-111">Value</span></span>|<span data-ttu-id="0bbd2-112">Architektur des Computers</span><span class="sxs-lookup"><span data-stu-id="0bbd2-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="0bbd2-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="0bbd2-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="0bbd2-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="0bbd2-114">0x014C</span></span>|<span data-ttu-id="0bbd2-115">x86</span><span class="sxs-lookup"><span data-stu-id="0bbd2-115">x86</span></span>|  
|<span data-ttu-id="0bbd2-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="0bbd2-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="0bbd2-117">0 x 0200</span><span class="sxs-lookup"><span data-stu-id="0bbd2-117">0x0200</span></span>|<span data-ttu-id="0bbd2-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="0bbd2-118">Intel IPF</span></span>|  
|<span data-ttu-id="0bbd2-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="0bbd2-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="0bbd2-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="0bbd2-120">0x8664</span></span>|<span data-ttu-id="0bbd2-121">x64</span><span class="sxs-lookup"><span data-stu-id="0bbd2-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bbd2-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0bbd2-122">Requirements</span></span>  
 <span data-ttu-id="0bbd2-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bbd2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bbd2-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0bbd2-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0bbd2-125">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="0bbd2-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0bbd2-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bbd2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bbd2-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bbd2-127">See Also</span></span>  
 [<span data-ttu-id="0bbd2-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0bbd2-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="0bbd2-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0bbd2-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="0bbd2-130">CorPEKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0bbd2-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
