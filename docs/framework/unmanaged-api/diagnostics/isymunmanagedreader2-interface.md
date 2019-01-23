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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08695c4e5df6aaa63bedecf68b741302e5ddd8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524939"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="fff75-102">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fff75-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="fff75-103">Stellt einen Symbolreader den Zugriff auf Dokumente, Methoden und Variablen in einem Symbolspeicher dar.</span><span class="sxs-lookup"><span data-stu-id="fff75-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="fff75-104">Diese Schnittstelle erweitert die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fff75-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fff75-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="fff75-105">Methods</span></span>  
  
|<span data-ttu-id="fff75-106">Methode</span><span class="sxs-lookup"><span data-stu-id="fff75-106">Method</span></span>|<span data-ttu-id="fff75-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fff75-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fff75-108">GetMethodByVersionPreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="fff75-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="fff75-109">Erhalten Sie ein Methodenobjekt des Symbolreaders, wenn ein Methodentoken und eine Versionsnummer mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fff75-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="fff75-110">GetMethodsInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="fff75-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="fff75-111">Ruft jede Methode, die in das angegebene Dokument über Zeileninformationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="fff75-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="fff75-112">GetSymAttributePreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="fff75-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="fff75-113">Ruft ein benutzerdefiniertes Attribut anhand seines Namens ab.</span><span class="sxs-lookup"><span data-stu-id="fff75-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fff75-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fff75-114">Requirements</span></span>  
 <span data-ttu-id="fff75-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fff75-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fff75-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fff75-116">See also</span></span>
- [<span data-ttu-id="fff75-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fff75-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="fff75-118">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fff75-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
