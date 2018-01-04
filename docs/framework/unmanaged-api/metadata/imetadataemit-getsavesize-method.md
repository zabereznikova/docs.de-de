---
title: IMetaDataEmit::GetSaveSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.GetSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7585f6adbca97b252fdad90276b0cd422d32c04a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="abe8e-102">IMetaDataEmit::GetSaveSize-Methode</span><span class="sxs-lookup"><span data-stu-id="abe8e-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="abe8e-103">Ruft die geschätzte binäre Größe der Assembly und die zugehörigen Metadaten im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="abe8e-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abe8e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="abe8e-104">Syntax</span></span>  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="abe8e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="abe8e-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="abe8e-106">[in] Der Wert der [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) -Enumeration, der angibt, ob eine genaue oder ungefähre Größe abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="abe8e-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="abe8e-107">Nur drei Werte sind gültig: CssAccurate, CssQuick und CssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="abe8e-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
-   <span data-ttu-id="abe8e-108">CssAccurate gibt die genaue Größe dauert jedoch länger zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="abe8e-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
-   <span data-ttu-id="abe8e-109">CssQuick gibt eine Größe aus, aus Sicherheitsgründen aufgefüllt, jedoch weniger Zeit zum Berechnen.</span><span class="sxs-lookup"><span data-stu-id="abe8e-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
-   <span data-ttu-id="abe8e-110">CssDiscardTransientCAs teilt `GetSaveSize` , entfernbare benutzerdefinierte Attribute ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="abe8e-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="abe8e-111">[out] Ein Zeiger auf die Größe, die zum Speichern der Datei erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="abe8e-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abe8e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="abe8e-112">Remarks</span></span>  
 <span data-ttu-id="abe8e-113">`GetSaveSize`berechnet den Speicherplatz in Bytes, der zum Speichern von der Assembly und alle zugehörigen Metadaten im aktuellen Bereich erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abe8e-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="abe8e-114">(Ein Aufruf der [IMetaDataEmit:: SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) Methode würde diese Anzahl von Bytes ausgegeben.)</span><span class="sxs-lookup"><span data-stu-id="abe8e-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="abe8e-115">Wenn der Aufrufer implementiert die [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) Schnittstelle (über [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) oder [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` zwei Durchläufen über die Metadaten zu optimieren und komprimieren.</span><span class="sxs-lookup"><span data-stu-id="abe8e-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="abe8e-116">Andernfalls werden keine Optimierungen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="abe8e-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="abe8e-117">Optimierung durchgeführt wird, sortiert die erste Übergabe einfach die Systemmetadaten-Strukturen, um die Leistung des Imports Suchvorgänge zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="abe8e-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="abe8e-118">Dieser Schritt führt in der Regel bei der Umstellung von Datensätzen mit dem Nebeneffekt, dass der Token, die vom Tool für die zukünftige Verwendung beibehalten für ungültig erklärt werden.</span><span class="sxs-lookup"><span data-stu-id="abe8e-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="abe8e-119">Die Metadaten informiert den Aufrufer diese token Änderungen erst nach dem zweiten Schritt jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="abe8e-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="abe8e-120">Im zweiten Schritt werden verschiedene Optimierungen durchgeführt, die auf die Gesamtgröße der Metadaten, z. B. Optimierung (frühes Binden) zu reduzieren `mdTypeRef` und `mdMemberRef` Token, wenn der Verweis auf einen Typ oder Member, die in deklariert wird die aktuellen Metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="abe8e-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="abe8e-121">In diesem Durchgang tritt auf, eine neue Reihe von token Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="abe8e-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="abe8e-122">Nach diesem Durchlauf benachrichtigt das Metadatenmodul für die den Aufrufer über seine `IMapToken` Schnittstelle, eines beliebigen token Werte geändert haben.</span><span class="sxs-lookup"><span data-stu-id="abe8e-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abe8e-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="abe8e-123">Requirements</span></span>  
 <span data-ttu-id="abe8e-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abe8e-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abe8e-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="abe8e-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="abe8e-126">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="abe8e-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abe8e-127">**.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abe8e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abe8e-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abe8e-128">See Also</span></span>  
 [<span data-ttu-id="abe8e-129">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="abe8e-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="abe8e-130">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="abe8e-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
