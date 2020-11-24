---
title: SetPEKind-Methode
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: be8a11cbf70e2c6f19ace67648b124515c1fb3c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680039"
---
# <a name="setpekind-method"></a><span data-ttu-id="bdb91-102">SetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="bdb91-102">SetPEKind Method</span></span>

<span data-ttu-id="bdb91-103">Bestimmt den Typ der portablen ausführbaren Datei, entweder Computer spezifisch oder Computer agnostisch.</span><span class="sxs-lookup"><span data-stu-id="bdb91-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdb91-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bdb91-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="bdb91-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bdb91-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="bdb91-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="bdb91-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="bdb91-107">Das Token der Datei, für die der PE-Typ festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bdb91-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="bdb91-108">Kann NULL sein, wenn `AssemblyID` kein ungebundenes NetModule angibt.</span><span class="sxs-lookup"><span data-stu-id="bdb91-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="bdb91-109">Der Typ des PE, wie von der [corpeer Kind-Enumeration](../metadata/corpekind-enumeration.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="bdb91-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="bdb91-110">Die Architektur des Ziel Computers, wie im NT-Header angegeben.</span><span class="sxs-lookup"><span data-stu-id="bdb91-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdb91-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bdb91-111">Return Value</span></span>  

 <span data-ttu-id="bdb91-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="bdb91-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdb91-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bdb91-113">Requirements</span></span>  

 <span data-ttu-id="bdb91-114">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="bdb91-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb91-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bdb91-115">See also</span></span>

- [<span data-ttu-id="bdb91-116">GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="bdb91-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="bdb91-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdb91-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="bdb91-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdb91-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="bdb91-119">ALink-API</span><span class="sxs-lookup"><span data-stu-id="bdb91-119">ALink API</span></span>](index.md)
