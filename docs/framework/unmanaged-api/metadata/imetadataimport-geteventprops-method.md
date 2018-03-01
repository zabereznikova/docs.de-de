---
title: IMetaDataImport::GetEventProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 73f257c46fd21355eeaabbe9e1b5d2841d2c3911
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="c0b8a-102">IMetaDataImport::GetEventProps-Methode</span><span class="sxs-lookup"><span data-stu-id="c0b8a-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="c0b8a-103">Ruft Metadateninformationen für das Ereignis durch das angegebene Ereignistoken, z. B. den deklarierenden Typ, hinzufügen und Entfernen von Entfernungsmethoden für Delegaten und alle Kennzeichnungen und sonstigen zugeordneten Daten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0b8a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0b8a-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="c0b8a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0b8a-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="c0b8a-106">[in] Das Ereignis-Metadatentoken, das das Ereignis beim Abrufen von Metadaten für darstellt.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="c0b8a-107">[out] Ein Zeiger auf das TypeDef-Token, das die Klasse darstellt, die das Ereignis deklariert.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="c0b8a-108">[out] Der Name des Ereignisses verweist `ev`.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="c0b8a-109">[in] Die angeforderte Länge in Breitzeichen `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="c0b8a-110">[out] Die zurückgegebene Länge in Breitzeichen `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="c0b8a-111">[out] Ein Zeiger auf ein TypeRef-Token oder TypeDef Metadaten token, die <xref:System.Delegate> Typ des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="c0b8a-112">[out] Ein Zeiger auf das Metadatentoken, das die Methode für die Handler für das Ereignis fügt darstellt.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="c0b8a-113">[out] Ein Zeiger auf das Metadatentoken, das die Methode für die Handler für das Ereignis entfernt darstellt.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="c0b8a-114">[out] Ein Zeiger auf das Metadatentoken der Methode, die das Ereignis auslöst darstellt.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="c0b8a-115">[out] Ein Array von token Zeigern auf andere Methoden, die dem Ereignis zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c0b8a-116">[in] Die maximale Größe des `rmdOtherMethod`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="c0b8a-117">[out] Die Anzahl der zurückgegebenen Token `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="c0b8a-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0b8a-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0b8a-118">Requirements</span></span>  
 <span data-ttu-id="c0b8a-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0b8a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0b8a-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0b8a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0b8a-121">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c0b8a-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0b8a-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0b8a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b8a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0b8a-123">See Also</span></span>  
 [<span data-ttu-id="c0b8a-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0b8a-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="c0b8a-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0b8a-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
