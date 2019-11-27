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
ms.openlocfilehash: 125a63638a41707b8eed918253cb1f93abb907eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434337"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="ff225-102">IMetaDataEmit::GetSaveSize-Methode</span><span class="sxs-lookup"><span data-stu-id="ff225-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="ff225-103">Ruft die geschätzte binäre Größe der Assembly und ihrer Metadaten im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="ff225-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff225-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff225-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff225-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff225-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="ff225-106">in Ein Wert der [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) -Enumeration, der angibt, ob eine genaue oder ungefähre Größe angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff225-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="ff225-107">Nur drei Werte sind gültig: cssexakten, cssQuick und cssverwerdtransientcas:</span><span class="sxs-lookup"><span data-stu-id="ff225-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
- <span data-ttu-id="ff225-108">cssexact gibt die genaue Speichergröße zurück, dauert aber länger für die Berechnung.</span><span class="sxs-lookup"><span data-stu-id="ff225-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
- <span data-ttu-id="ff225-109">cssQuick gibt eine Größe zurück, die für die Sicherheit aufgefüllt ist, aber weniger Zeit für die Berechnung benötigt.</span><span class="sxs-lookup"><span data-stu-id="ff225-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
- <span data-ttu-id="ff225-110">cssverwerdtransientcas weist `GetSaveSize` an, dass Sie verwertbare benutzerdefinierte Attribute verwerfen kann.</span><span class="sxs-lookup"><span data-stu-id="ff225-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="ff225-111">vorgenommen Ein Zeiger auf die Größe, die zum Speichern der Datei erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ff225-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff225-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff225-112">Remarks</span></span>  
 <span data-ttu-id="ff225-113">`GetSaveSize` berechnet den erforderlichen Speicherplatz (in Bytes), um die Assembly und alle zugehörigen Metadaten im aktuellen Bereich zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ff225-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="ff225-114">(Ein Aufrufe der [IMetaDataEmit:: savedestream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) -Methode würde diese Anzahl von Bytes ausgeben.)</span><span class="sxs-lookup"><span data-stu-id="ff225-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="ff225-115">Wenn der Aufrufer die [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) -Schnittstelle implementiert (über [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) oder [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), führt `GetSaveSize` zwei Durchgänge über die Metadaten aus, um ihn zu optimieren und zu komprimieren.</span><span class="sxs-lookup"><span data-stu-id="ff225-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="ff225-116">Andernfalls werden keine Optimierungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ff225-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="ff225-117">Wenn die Optimierung durchgeführt wird, sortiert der erste Durchlauf einfach die Metadatenstrukturen, um die Leistung von Import Zeit suchen zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="ff225-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="ff225-118">Dieser Schritt führt in der Regel dazu, dass Datensätze verschoben werden, mit dem Nebeneffekt, dass Token, die vom Tool für zukünftige Verweise aufbewahrt werden, ungültig werden.</span><span class="sxs-lookup"><span data-stu-id="ff225-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="ff225-119">Die Metadaten informieren den Aufrufer über diese Tokenänderungen erst nach dem zweiten Durchlauf.</span><span class="sxs-lookup"><span data-stu-id="ff225-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="ff225-120">Im zweiten Durchlauf werden verschiedene Optimierungen ausgeführt, mit denen die Gesamtgröße der Metadaten reduziert werden soll, z. b. die Optimierung von (frühe Bindung) `mdTypeRef` und `mdMemberRef` Tokens, wenn der Verweis auf einen Typ oder Member ist, der im aktuellen Metadatenbereich deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="ff225-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="ff225-121">In diesem Durchlauf erfolgt eine weitere Runde der Tokenzuordnung.</span><span class="sxs-lookup"><span data-stu-id="ff225-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="ff225-122">Nach diesem Durchlauf benachrichtigt die metadatenengine den Aufrufer über seine `IMapToken`-Schnittstelle über geänderte Tokenwerte.</span><span class="sxs-lookup"><span data-stu-id="ff225-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff225-123">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ff225-123">Requirements</span></span>  
 <span data-ttu-id="ff225-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff225-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff225-125">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ff225-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff225-126">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff225-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff225-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff225-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff225-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff225-128">See also</span></span>

- [<span data-ttu-id="ff225-129">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff225-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ff225-130">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff225-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
