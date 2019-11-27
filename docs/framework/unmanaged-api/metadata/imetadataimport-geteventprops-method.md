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
ms.openlocfilehash: 18fe0c834506d0ac4cd15fd7af4c4f15904b0f81
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437585"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="36ef5-102">IMetaDataImport::GetEventProps-Methode</span><span class="sxs-lookup"><span data-stu-id="36ef5-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="36ef5-103">Ruft Metadateninformationen für das Ereignis ab, das durch das angegebene Ereignis Token dargestellt wird, einschließlich des deklarierenden Typs, der Add-und Remove-Methoden für Delegaten sowie aller Flags und anderer zugeordneter Daten.</span><span class="sxs-lookup"><span data-stu-id="36ef5-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36ef5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="36ef5-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="36ef5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="36ef5-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="36ef5-106">in Das Ereignis Metadatentoken, das das Ereignis darstellt, für das Metadaten zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="36ef5-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="36ef5-107">vorgenommen Ein Zeiger auf das TypeDef-Token, das die Klasse darstellt, die das Ereignis deklariert.</span><span class="sxs-lookup"><span data-stu-id="36ef5-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="36ef5-108">vorgenommen Der Name des Ereignisses, auf das von `ev`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="36ef5-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="36ef5-109">in Die angeforderte Länge in breit Zeichen `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="36ef5-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="36ef5-110">vorgenommen Die zurückgegebene Länge in breit Zeichen `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="36ef5-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="36ef5-111">vorgenommen Ein Zeiger auf ein TypeRef-oder TypeDef-Metadatentoken, das den <xref:System.Delegate> Typ des Ereignisses darstellt.</span><span class="sxs-lookup"><span data-stu-id="36ef5-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="36ef5-112">vorgenommen Ein Zeiger auf das Metadatentoken, das die Methode darstellt, mit der Handler für das Ereignis hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="36ef5-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="36ef5-113">vorgenommen Ein Zeiger auf das Metadatentoken, das die Methode darstellt, die Handler für das Ereignis entfernt.</span><span class="sxs-lookup"><span data-stu-id="36ef5-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="36ef5-114">vorgenommen Ein Zeiger auf das Metadatentoken, das die Methode darstellt, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="36ef5-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="36ef5-115">vorgenommen Ein Array von Tokenzeigern auf andere Methoden, die dem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="36ef5-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="36ef5-116">[in] Die maximale Größe des `rmdOtherMethod`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="36ef5-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="36ef5-117">vorgenommen Die Anzahl der in `rmdOtherMethod`zurückgegebenen Token.</span><span class="sxs-lookup"><span data-stu-id="36ef5-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36ef5-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="36ef5-118">Requirements</span></span>  
 <span data-ttu-id="36ef5-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36ef5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36ef5-120">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="36ef5-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36ef5-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="36ef5-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36ef5-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ef5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ef5-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36ef5-123">See also</span></span>

- [<span data-ttu-id="36ef5-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36ef5-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="36ef5-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36ef5-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
