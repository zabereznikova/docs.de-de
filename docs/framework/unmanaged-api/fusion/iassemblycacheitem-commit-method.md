---
title: IAssemblyCacheItem::Commit-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.Commit
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 380181d8e309ba4b51d49aae9159f0bbf7e0250f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796718"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="61aee-102">IAssemblyCacheItem::Commit-Methode</span><span class="sxs-lookup"><span data-stu-id="61aee-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="61aee-103">Führt einen Commit für den zwischengespeicherten Assemblyverweis zum</span><span class="sxs-lookup"><span data-stu-id="61aee-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61aee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61aee-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61aee-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61aee-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="61aee-106">in In Fusion. idl definierte Flags.</span><span class="sxs-lookup"><span data-stu-id="61aee-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="61aee-107">[out, optional] Ein-Wert, der das Ergebnis des Vorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="61aee-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61aee-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61aee-108">Requirements</span></span>  
 <span data-ttu-id="61aee-109">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61aee-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61aee-110">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="61aee-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="61aee-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61aee-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61aee-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61aee-112">See also</span></span>

- [<span data-ttu-id="61aee-113">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61aee-113">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
