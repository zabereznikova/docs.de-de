---
title: IMetaDataImport::GetEventProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c87f2212c761dc31a75addabca6970c5497aa2a0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782426"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="fc79a-102">IMetaDataImport::GetEventProps-Methode</span><span class="sxs-lookup"><span data-stu-id="fc79a-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="fc79a-103">Ruft Metadateninformationen für das Ereignis durch, einschließlich der deklarierende Typ, hinzufügen und Entfernungsmethoden für Delegaten, und alle Flags und sonstigen zugeordneten Daten das angegebene Ereignistoken dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fc79a-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc79a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc79a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,   
   [out] LPCWSTR       szEvent,   
   [in]  ULONG         cchEvent,   
   [out] ULONG         *pchEvent,   
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,   
   [out] mdMethodDef   *pmdRemoveOn,   
   [out] mdMethodDef   *pmdFire,   
   [out] mdMethodDef   rmdOtherMethod[],   
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc79a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fc79a-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="fc79a-106">[in] Das Ereignis-Metadatentoken, das das Ereignis, das Abrufen von Metadaten für darstellt.</span><span class="sxs-lookup"><span data-stu-id="fc79a-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="fc79a-107">[out] Ein Zeiger auf das TypeDef-Token, die die Klasse darstellt, die das Ereignis deklariert.</span><span class="sxs-lookup"><span data-stu-id="fc79a-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="fc79a-108">[out] Der Name des Ereignisses verweist `ev`.</span><span class="sxs-lookup"><span data-stu-id="fc79a-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="fc79a-109">[in] Die angeforderte Länge in Breitzeichen `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="fc79a-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="fc79a-110">[out] Die zurückgegebene Länge in Breitzeichen `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="fc79a-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="fc79a-111">[out] Ein Zeiger auf ein TypeRef oder TypeDef Metadaten token, die <xref:System.Delegate> der Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="fc79a-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="fc79a-112">[out] Ein Zeiger auf das Metadatentoken, das die Methode, die fügt Handler für das Ereignis darstellt.</span><span class="sxs-lookup"><span data-stu-id="fc79a-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="fc79a-113">[out] Ein Zeiger auf das Metadatentoken, das die Methode, die Handler für das Ereignis entfernt darstellt.</span><span class="sxs-lookup"><span data-stu-id="fc79a-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="fc79a-114">[out] Ein Zeiger auf das Metadatentoken, das die Methode, die das Ereignis auslöst darstellt.</span><span class="sxs-lookup"><span data-stu-id="fc79a-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="fc79a-115">[out] Ein Array von Sicherheitstoken Verweise auf andere Methoden, die dem Ereignis zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fc79a-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fc79a-116">[in] Die maximale Größe des `rmdOtherMethod`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="fc79a-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="fc79a-117">[out] Die Anzahl der in zurückgegebenen Token `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="fc79a-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc79a-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fc79a-118">Requirements</span></span>  
 <span data-ttu-id="fc79a-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc79a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc79a-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fc79a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc79a-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fc79a-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fc79a-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc79a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc79a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc79a-123">See also</span></span>

- [<span data-ttu-id="fc79a-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc79a-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fc79a-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc79a-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
