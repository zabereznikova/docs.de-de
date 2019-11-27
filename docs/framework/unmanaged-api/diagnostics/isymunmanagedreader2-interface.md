---
title: ISymUnmanagedReader2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: a07c75e14244fb5bdf72ff2b0d344ae27672ef89
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448270"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="deb92-102">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="deb92-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="deb92-103">Stellt einen Symbol Reader dar, der den Zugriff auf Dokumente, Methoden und Variablen in einem Symbol Speicher ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="deb92-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="deb92-104">Diese Schnittstelle erweitert die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="deb92-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="deb92-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="deb92-105">Methods</span></span>  
  
|<span data-ttu-id="deb92-106">Methode</span><span class="sxs-lookup"><span data-stu-id="deb92-106">Method</span></span>|<span data-ttu-id="deb92-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="deb92-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="deb92-108">GetMethodByVersionPreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="deb92-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="deb92-109">Sie erhalten eine Symbol Lesemethode, wenn Sie über ein Methoden Token und eine Edit-and-Continue-Versionsnummer verfügen.</span><span class="sxs-lookup"><span data-stu-id="deb92-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="deb92-110">GetMethodsInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="deb92-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="deb92-111">Ruft jede Methode ab, die im angegebenen Dokument über Zeilen Informationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="deb92-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="deb92-112">GetSymAttributePreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="deb92-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="deb92-113">Ruft ein benutzerdefiniertes Attribut basierend auf seinem Namen ab.</span><span class="sxs-lookup"><span data-stu-id="deb92-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="deb92-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="deb92-114">Requirements</span></span>  
 <span data-ttu-id="deb92-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="deb92-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb92-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="deb92-116">See also</span></span>

- [<span data-ttu-id="deb92-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="deb92-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="deb92-118">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="deb92-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
