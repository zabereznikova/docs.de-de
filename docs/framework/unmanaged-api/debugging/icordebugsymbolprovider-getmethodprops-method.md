---
title: ICorDebugSymbolProvider::GetMethodProps-Methode
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
ms.openlocfilehash: c9e73c4de7389405d9e4b643036709ff2dbb82e6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379567"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="4f035-102">ICorDebugSymbolProvider::GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4f035-102">ICorDebugSymbolProvider::GetMethodProps Method</span></span>
<span data-ttu-id="4f035-103">Gibt Informationen zu Methodeneigenschaften wie das Metadatentoken der Methode und Informationen zu den generischen Parametern der Methode zurück, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="4f035-103">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f035-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f035-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f035-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f035-105">Parameters</span></span>  
 `codeRVA`  
 <span data-ttu-id="4f035-106">[in] Eine relative virtuelle Adresse in der Methode, zu der Informationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4f035-106">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="4f035-107">[out] Ein Zeiger auf das Metadatentoken der Methode.</span><span class="sxs-lookup"><span data-stu-id="4f035-107">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="4f035-108">[out] Ein Zeiger auf die Anzahl der generischen Parameter, die dieser Methode zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4f035-108">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="4f035-109">[in] Die Größe des `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="4f035-109">[in] The size of the `signature` array.</span></span> <span data-ttu-id="4f035-110">Weitere Informationen finden Sie im Abschnitt mit den Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="4f035-110">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="4f035-111">[out] Ein Zeiger auf die Größe des zurückgegebenen `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="4f035-111">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="4f035-112">[out] Ein Puffer, der die TypeSpec-Signaturen aller generischen Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="4f035-112">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f035-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f035-113">Remarks</span></span>  
 <span data-ttu-id="4f035-114">Um die erforderliche Größe des Arrays der Methode zu erhalten `signature` , legen Sie das- `cbSignature` Argument auf 0 und `signature` auf **null**fest.</span><span class="sxs-lookup"><span data-stu-id="4f035-114">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="4f035-115">Wenn die Methode zurückgegeben wird, enthält `pcbSignature` die Anzahl der für das `signature`-Array erforderlichen Bytes.</span><span class="sxs-lookup"><span data-stu-id="4f035-115">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f035-116">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4f035-116">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f035-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4f035-117">Requirements</span></span>  
 <span data-ttu-id="4f035-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f035-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f035-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f035-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f035-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f035-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f035-121">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f035-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f035-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f035-122">See also</span></span>

- [<span data-ttu-id="4f035-123">GetTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4f035-123">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)
- [<span data-ttu-id="4f035-124">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f035-124">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4f035-125">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4f035-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
