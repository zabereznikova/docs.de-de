---
title: IMetaDataEmit::GetSaveSize-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9279808e4ad15b693d06ac8a99dd33a609e5a8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992510"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="24f5e-102">IMetaDataEmit::GetSaveSize-Methode</span><span class="sxs-lookup"><span data-stu-id="24f5e-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="24f5e-103">Ruft die binäre geschätzte Größe der Assembly und die Metadaten im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="24f5e-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f5e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24f5e-104">Syntax</span></span>  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24f5e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="24f5e-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="24f5e-106">[in] Der Wert der [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) -Enumeration, der angibt, ob eine genaue oder ungefähre Größe erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="24f5e-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="24f5e-107">Nur drei Werte sind gültig: CssAccurate, CssQuick und CssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="24f5e-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
- <span data-ttu-id="24f5e-108">CssAccurate gibt die genaue Größe dauert jedoch länger zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="24f5e-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
- <span data-ttu-id="24f5e-109">CssQuick gibt eine Größe aus, aus Sicherheitsgründen aufgefüllt, jedoch weniger Zeit zum Berechnen.</span><span class="sxs-lookup"><span data-stu-id="24f5e-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
- <span data-ttu-id="24f5e-110">CssDiscardTransientCAs teilt `GetSaveSize` , entfernbare benutzerdefinierte Attribute ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="24f5e-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="24f5e-111">[out] Ein Zeiger auf die Größe, die zum Speichern der Datei erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="24f5e-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24f5e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24f5e-112">Remarks</span></span>  
 <span data-ttu-id="24f5e-113">`GetSaveSize` berechnet den Speicherplatz in Bytes, der zum Speichern von der Assembly und alle seine Metadaten im aktuellen Bereich erforderlich.</span><span class="sxs-lookup"><span data-stu-id="24f5e-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="24f5e-114">(Ein Aufruf der [IMetaDataEmit:: SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) Methode würde diese Anzahl von Bytes ausgegeben.)</span><span class="sxs-lookup"><span data-stu-id="24f5e-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="24f5e-115">Wenn der Aufrufer implementiert die [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) Schnittstelle (über [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) oder [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` führt zwei Durchläufe über die Metadaten zum Optimieren und zu komprimieren.</span><span class="sxs-lookup"><span data-stu-id="24f5e-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="24f5e-116">Andernfalls werden keine Optimierungen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="24f5e-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="24f5e-117">Wenn die Optimierung ausgeführt wird, sortiert im ersten Durchlauf einfach die Systemmetadaten-Strukturen, um die Leistung der Imports Suchvorgänge zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="24f5e-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="24f5e-118">Dieser Schritt führt in der Regel bei der Umstellung von Datensätzen, mit dem Nebeneffekt, dass Token vom Tool für die zukünftige Verwendung beibehalten ungültig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="24f5e-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="24f5e-119">Die Metadaten informiert den Aufrufer diese token Änderungen erst nach dem im zweiten Durchlauf jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="24f5e-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="24f5e-120">Im zweiten Durchlauf, zahlreiche Optimierungen durchgeführt, die die Gesamtgröße der Metadaten, z. B. Optimierung (frühes Binden) zu reduzieren vorgesehen sind `mdTypeRef` und `mdMemberRef` Token, wenn der Verweis auf einen Typ oder Member, der in deklariert wird die aktuellen Metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="24f5e-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="24f5e-121">In diesem Schritt tritt auf, eine weitere runde der token-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="24f5e-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="24f5e-122">Nach diesem Durchlauf der Metadaten-Engine benachrichtigt den Aufrufer über die `IMapToken` -Schnittstelle über token Werte geändert haben.</span><span class="sxs-lookup"><span data-stu-id="24f5e-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24f5e-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24f5e-123">Requirements</span></span>  
 <span data-ttu-id="24f5e-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24f5e-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24f5e-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="24f5e-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24f5e-126">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="24f5e-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24f5e-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24f5e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f5e-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24f5e-128">See also</span></span>

- [<span data-ttu-id="24f5e-129">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24f5e-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="24f5e-130">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24f5e-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
