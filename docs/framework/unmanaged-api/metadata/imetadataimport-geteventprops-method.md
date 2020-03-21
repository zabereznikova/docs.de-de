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
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177273"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="89a15-102">IMetaDataImport::GetEventProps-Methode</span><span class="sxs-lookup"><span data-stu-id="89a15-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="89a15-103">Ruft Metadateninformationen für das Ereignis ab, das durch das angegebene Ereignistoken dargestellt wird, einschließlich des deklarierenden Typs, der Add- und Remove-Methoden für Delegaten sowie aller Flags und anderer zugeordneter Daten.</span><span class="sxs-lookup"><span data-stu-id="89a15-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89a15-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89a15-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="89a15-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="89a15-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="89a15-106">[in] Das Ereignismetadatentoken, das das Ereignis darstellt, für das Metadaten abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89a15-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="89a15-107">[out] Ein Zeiger auf das TypeDef-Token, das die Klasse darstellt, die das Ereignis deklariert.</span><span class="sxs-lookup"><span data-stu-id="89a15-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="89a15-108">[out] Der Name des Ereignisses, auf das von `ev`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="89a15-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="89a15-109">[in] Die angeforderte Länge `szEvent`in breiten Zeichen von .</span><span class="sxs-lookup"><span data-stu-id="89a15-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="89a15-110">[out] Die zurückgegebene Länge `szEvent`in breiten Zeichen von .</span><span class="sxs-lookup"><span data-stu-id="89a15-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="89a15-111">[out] Ein Zeiger auf ein TypeRef- oder <xref:System.Delegate> TypeDef-Metadatentoken, das den Typ des Ereignisses darstellt.</span><span class="sxs-lookup"><span data-stu-id="89a15-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="89a15-112">[out] Ein Zeiger auf das Metadatentoken, das die Methode darstellt, die Handler für das Ereignis hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="89a15-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="89a15-113">[out] Ein Zeiger auf das Metadatentoken, das die Methode darstellt, die Handler für das Ereignis entfernt.</span><span class="sxs-lookup"><span data-stu-id="89a15-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="89a15-114">[out] Ein Zeiger auf das Metadatentoken, das die Methode darstellt, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="89a15-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="89a15-115">[out] Ein Array von Tokenzeigern auf andere Methoden, die dem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="89a15-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="89a15-116">[in] Die maximale Größe des `rmdOtherMethod`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="89a15-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="89a15-117">[out] Die Anzahl der Token, die in `rmdOtherMethod`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="89a15-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89a15-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="89a15-118">Requirements</span></span>  
 <span data-ttu-id="89a15-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89a15-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89a15-120">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89a15-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89a15-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="89a15-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89a15-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89a15-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a15-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89a15-123">See also</span></span>

- [<span data-ttu-id="89a15-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89a15-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="89a15-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89a15-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
